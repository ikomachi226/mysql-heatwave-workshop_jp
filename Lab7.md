# Lab 7 - Execute queries using Heatwave

_**7.1 -**_ On the OCI console, check that HeatWave nodes are in _**Active**_ status.
![](./images/HW34_hw.png)

_**7.2 -**_ If HeatWave nodes are in "Active" status, you can load the tpch database tables into HeatWave, from your bastion host ssh connection, using the following command:
```
mysqlsh --user=admin --password=Oracle.123 --host=<mysql_private_ip_address> --port=3306 --sql < tpch_offload.sql
```

Note: The tpch_offload.sql scripts, apart from applying dictionary encoding to a some columns using _**'RAPID_COLUMN=ENCODING=SORTED'**_ (optional step), loads the tables into HeatWave setting the following values:
```
alter table <table_name> secondary_engine=rapid;
alter table  <table_name> secondary_load;
```
Additionally you can inspect the full content of the file, executing, from the Linux shell:
```
cat tpch_offload.sql
```

_**7.3 -**_ If the previous step completed without errors, you are good to go!

_**7.4 -**_ Let's come back to the previous query and execute it this time using HeatWave.

Connect to MySQL DB System:
```
mysqlsh --user=admin --password=Oracle.123 --host=<mysql_private_ip_address> --port=3306 --database=tpch --sql
```

Enable HeatWave:
```
set @@use_secondary_engine=ON;
```

Check the explain plan of the previous query and confirm it will be using secondary engine:
```
EXPLAIN SELECT
    l_returnflag,
    l_linestatus,
    SUM(l_quantity) AS sum_qty,
    SUM(l_extendedprice) AS sum_base_price,
    SUM(l_extendedprice * (1 - l_discount)) AS sum_disc_price,
    SUM(l_extendedprice * (1 - l_discount) * (1 + l_tax)) AS sum_charge,
    AVG(l_quantity) AS avg_qty,
    AVG(l_extendedprice) AS avg_price,
    AVG(l_discount) AS avg_disc,
    COUNT(*) AS count_order
FROM
    lineitem
WHERE
    l_shipdate <= DATE '1998-12-01' - INTERVAL '90' DAY
GROUP BY l_returnflag , l_linestatus
ORDER BY l_returnflag , l_linestatus;
```
(Look for the message "Using secondary engine RAPID" in the output)


Re-run the previous query and check the execution time again:
```
SELECT
    l_returnflag,
    l_linestatus,
    SUM(l_quantity) AS sum_qty,
    SUM(l_extendedprice) AS sum_base_price,
    SUM(l_extendedprice * (1 - l_discount)) AS sum_disc_price,
    SUM(l_extendedprice * (1 - l_discount) * (1 + l_tax)) AS sum_charge,
    AVG(l_quantity) AS avg_qty,
    AVG(l_extendedprice) AS avg_price,
    AVG(l_discount) AS avg_disc,
    COUNT(*) AS count_order
FROM
    lineitem
WHERE
    l_shipdate <= DATE '1998-12-01' - INTERVAL '90' DAY
GROUP BY l_returnflag , l_linestatus
ORDER BY l_returnflag , l_linestatus;
```

This time execution time should be about 0.2-0.5s!!

Exit from MySQL Shell:
```
\exit
```

_**7.5 -**_ Now that you have understood how HeatWave offloading works and which performance gain it can give, it is time to run some batch execution.

We will run the script tpch_queries_mysql.sql to execute some queries without using HeatWave.
Then, we will run the script tpch_queries_rapid.sql to execute the same queries using HeatWave.
In the end, we will compare the results.

For this excercise, instead of MySQL Shell, we will use MySQL client:
Run the following commands:
```
mysql -h<mysql ip addr> -uadmin -pOracle.123 -Dtpch < tpch_queries_rapid.sql
mysql -h<mysql ip addr> -uadmin -pOracle.123 -Dtpch < tpch_queries_mysql.sql
diff -y rapid_rt_profiles.log mysql_rt_profiles.log
```

The output of the last command should look as follows:

```
Query_ID	Duration	Query				Query_ID	Duration	Query
1	0.43741500	SELECT \n    l_returnflag,\n    l_lin |	1	13.34447075	SELECT \n    l_returnflag,\n    l_lin
2	0.05510250	SELECT \n    l_orderkey,\n    SUM(l_e |	2	2.81767825	SELECT \n    l_orderkey,\n    SUM(l_e
3	0.03569350	SELECT \n    O_ORDERPRIORITY, COUNT(* |	3	0.67656550	SELECT \n    O_ORDERPRIORITY, COUNT(*
4	0.29090700	SELECT \n    n_name, SUM(l_extendedpr |	4	3.43357100	SELECT \n    n_name, SUM(l_extendedpr
5	0.01475100	SELECT \n    SUM(l_extendedprice * l_ |	5	1.92334425	SELECT \n    SUM(l_extendedprice * l_
6	0.12739250	SELECT \n    supp_nation, cust_nation |	6	2.91310275	SELECT \n    supp_nation, cust_nation
7	0.05971975	SELECT \n    o_year,\n    SUM(CASE\n  |	7	2.32921225	SELECT \n    o_year,\n    SUM(CASE\n 
8	0.09896975	SELECT \n    nation, o_year, SUM(amou |	8	6.26314100	SELECT \n    nation, o_year, SUM(amou
9	0.04798775	SELECT \n    c_custkey,\n    c_name,\ |	9	1.26776875	SELECT \n    c_custkey,\n    c_name,\
10	0.10815325	SELECT \n    PS_PARTKEY, SUM(PS_SUPPL |	10	0.43670475	SELECT \n    PS_PARTKEY, SUM(PS_SUPPL
11	0.02604025	SELECT \n    l_shipmode,\n    SUM(CAS |	11	2.56930425	SELECT \n    l_shipmode,\n    SUM(CAS
12	0.05837475	SELECT \n    c_count, COUNT(*) AS cus |	12	2.04714750	SELECT \n    c_count, COUNT(*) AS cus
13	0.02064350	SELECT \n    100.00 * SUM(CASE\n      |	13	1.95272375	SELECT \n    100.00 * SUM(CASE\n     
14	0.02863725	WITH REVENUE0 AS (\nSELECT \n    L_SU |	14	2.08620250	WITH REVENUE0 AS (\nSELECT \n    L_SU
15	0.12952825	SELECT \n    P_BRAND,\n    P_TYPE,\n  |	15	0.31044925	SELECT \n    P_BRAND,\n    P_TYPE,\n 
16	0.15458875	SELECT \n    C_NAME,\n    C_CUSTKEY,\ |	16	2.54871800	SELECT \n    C_NAME,\n    C_CUSTKEY,\
17	0.02226300	SELECT \n    SUM(l_extendedprice * (1 |	17	773.58222775	SELECT \n    SUM(l_extendedprice * (1
18	0.05721275	SELECT \n    CNTRYCODE, COUNT(*) AS N |	18	0.75508325	SELECT \n    CNTRYCODE, COUNT(*) AS N
```

Now, you can compare the execution times obtained using HeatWave or only MySQL on InnoDB.

Optional: inspect the tpch_queries_mysql.sql and the tpch_queries_rapid.sql scripts using vi.


## Great Work - All Done!
