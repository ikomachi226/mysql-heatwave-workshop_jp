# Lab 6 - Import data into MDS and load tables to HeatWave

_**6.1 -**_ Go back to your cloud shell ssh connection to the bastion host.

_**6.2 -**_ Connect to MySQL DB System using MySQL Shell, with the following command:
```
mysqlsh --user=admin --password=Oracle.123 --host=<mysql_private_ip_address> --port=3306 --js
```

_**6.3 -**_ From the MySQL Shell connection, import the data set into MySQL DB System:
```
util.loadDump("/home/opc/tpch_dump", {dryRun: true, resetProgress:true, ignoreVersion:true})
```

_**6.4 -**_ Check the imported data. From MySQL Shell execute the commands:

```
\sql

SHOW DATABASES;
```
(You shoul see the following output:)
```
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| tpch               |
+--------------------+
```
```
USE TPCH;

SHOW TABLES;
```
(You shoul see the following output:)
```
+----------------+
| Tables_in_tpch |
+----------------+
| customer       |
| lineitem       |
| nation         |
| orders         |
| part           |
| partsupp       |
| region         |
| supplier       |
+----------------+

\exit
```

_**6.5 -**_ Connect to MySQL DB System:
```
mysqlsh --user=admin --password=Oracle.123 --host=<mysql_private_ip_address> --port=3306 --database=tpch --sql
```

_**6.6 -**_ Let's start testing a simple query.
Run the following query and check the execution time (approximately 12-13s):
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


**[Go to the next Lab](Lab7.md)**
