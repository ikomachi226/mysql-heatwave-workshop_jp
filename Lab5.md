# Lab 5: Add HeatWave cluster to MySQL Database Service

## Key Objectives:
- Learn how to enable the HeatWave cluster for MDS


## Introduction

HeatWave enables provisioning of HeatWave clusters for accelerated processing of analytic queries. A HeatWave cluster consists of a MySQL DB System node and two or more HeatWave nodes. The MySQL DB System node includes a HeatWave plugin that is responsible for cluster management, query scheduling, and returning query results to the MySQL DB System. HeatWave nodes store data in memory and process queries.

When a HeatWave cluster is enabled, queries that meet certain prerequisites are automatically offloaded from the MySQL DB System to the HeatWave cluster for accelerated execution. Queries are issued from a MySQL client or application that interacts with the HeatWave cluster by connecting to the MySQL DB System node. Results are returned to the MySQL DB System node and to the MySQL client or application that issued the query. 
After deploying a HeatWave cluster, refer to the **[HeatWave User's Guide](https://dev.mysql.com/doc/heatwave/en/)** for information about how to load data and run queries. 

## Steps

### **Step 5.1:**
- In the menu on the left, go to _**Databases >> DB Systems**_
Click on the DB System which you have previously created and verify that status is _**Active**_.
Take note of the _**Private IP Address**_ of the MySQL DB System.

![](./images/HW29_mds.png)

### **Step 5.2:**
- Scroll down and select _**HeatWave**_ from the menu on the left.
  
![](./images/HW30_hw.png)

### **Step 5.3:**
- Click on the button _**Add HeatWave Cluster**_ located on the right.
  
![](./images/HW31_hw.png)

### **Step 5.4:**
- Check that Shape looks as per picture below and that Node Count is set to 2.
Click the blue button _**Add HeatWave Cluster**_

![](./images/HW32_hw.png)

### **Step 5.5:**
- 5 You will be brought back to the main page where you can check for the creation status. After some seconds you should see the nodes in _**Creating**_ status.
  
![](./images/HW33_hw.png)

### **Step 5.6:**
- After completion, the node status will switch to _**Active**_ status. The process will take some time to be completed. 
  
![](./images/HW34_hw.png)

## Conclusion

Now we have created HeatWave cluster, that consists of a MySQL DB System node and two or more HeatWave nodes.The MySQL DB System node includes a HeatWave plugin that is responsible for cluster management, query scheduling, and returning query results to the MySQL DB System. HeatWave nodes store data in memory and process queries. 
Learn more about **[HeatWave service on Oracle Cloud](https://docs.oracle.com/en-us/iaas/mysql-database/doc/heatwave1.html)** 
So let's connect to MySQL DB System and run some queries before we enable the HeatWave cluster in the next lab! 

**[<< Go to Lab 4](Lab4.md)** | **[Home](Readme.md)** | **[Go to Lab 6 >>](Lab6.md)**
