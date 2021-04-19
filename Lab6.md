# Lab 6: Import data into MDS and load tables to HeatWave

## Key Objectives:
- Learn how to import the downloaded data set into MySQL DB System using cloud shell.
- Run query without Heatwave service enabled to note the execution time .

## Steps

### **Step 6.1:**
- Go back to your ssh connection to the bastion host.

![](./images/HW35_hw.png)

### **Step 6.2:**
- Connect to MySQL DB System using MySQL Shell, with the following command:
```
mysqlsh --user=admin --password=Oracle.123 --host=<mysql_private_ip_address> --port=3306 --js
```

### **Step 6.3:**
- From the MySQL Shell connection, import the data set into MySQL DB System:
```
util.loadDump("/home/opc/tpch_dump", {dryRun: true, resetProgress:true, ignoreVersion:true})
```
This command will run a dry run of the import. If it terminates without errors, execute the followin to load the dump for real:
```
util.loadDump("/home/opc/tpch_dump", {dryRun: false, resetProgress:true, ignoreVersion:true})
```

### **Step 6.4:**
- Check the imported data. From MySQL Shell execute the commands:

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
Continue with commands:
```
USE tpch;

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
```

### **Step 6.5:**
- Let's start testing a simple query but yet effective query.
From the previous SQL prompt, run the following query and check the execution time (approximately 12-13s):
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

## Conclusion

As we can see the time consumed to run the query is relatively long, so let's enable Heatwave service and run the query again to compare the result **[in the next Lab!](Lab7.md)**
