# Lab 8b: Deploy your mission critical application on MDS High Availability

## Key Objectives:

- Learn how to create MDS instance with High Availability configuration

## Introduction

MDS provides _**High Availability**_ to mission critical application that demands zero data loss. A HA-enabled MDS contains three MySQL instances deployed across different availability or fault domains. Your data is replicated using MySQL Group Replication. Your application connects to a single endpoint to read and write data to the database. In the event of a failure, the DB System will automatically failover to a secondary instance without requiring a reconfiguration of the application.
For an overview of MDS High Availability, check **[MDS High Availability](https://docs.oracle.com/en-us/iaas/mysql-database/doc/business-continuity.html#MYAAS-GUID-2CD8BFB9-30B2-4ED5-BE27-E526DD3F6E0A)**.

## Steps

### **Step 1.1:**
  Log-in to your OCI tenancy. Once you have logged-in, select _**Database >> MySQL >> DB Systems**_ from the _**menu icon**_ on the top left corner
  
![](./images/ha-1.png)

### **Step 1.2:**
 Click on _**Create MySQL DB Systems**_

![](./images/ha-2.png)

### **Step 1.3:** 
 Select _**High Availability**_ configuration, and fill up the details of the following fields:
 * _**Create in compartment**_: your compartment
 * _**Name**_: name of MDS intance (eg MDS_HA)
 * _**Description**_: description of the usage of MDS instance
 * _**Username**_: name of MDS database administrator (eg admin)
 * _**Password**_: a secured password that you can remember

![](./images/ha-3.png)

### **Step 1.3:** 
 Select _**Virtual Cloud Network**_ (by default, the private subnet in your Virtual Cloud Network will be selected)
 
 ![](./images/ha-4.png)

### **Step 1.4:**
 Click on _**Create**_ to create the MDS High Availabilty configuration, you should be able to use MDS HA in a few minutes once it is provisioned. Enjoy!
 
 ![](./images/ha-5.png)
 



