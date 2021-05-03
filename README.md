# MySQL Database Service powered by HeatWave for your Analytics project on Oracle Cloud

This workshop will walk you through the process to deploy and configure MySQL Database Service & Heatwave to run Analytics workloads in Oracle Cloud. 
 
HeatWave is a new, integrated, high-performance analytics engine for MySQL Database Service. HeatWave accelerates MySQL performance by 400X for analytics queries, scales out to thousands of cores, and is 2.7X faster at one-third the cost of Amazon Redshift. MySQL Database Service, with HeatWave, is the only service that enables database admins and app developers to run OLTP and OLAP workloads directly from their MySQL database, eliminating the need for complex, time-consuming, and expensive data movement and integration with a separate analytics database. The service is optimized for and exclusively available in Oracle Cloud Infrastructure (OCI).
 
At the end of the workshop you will be able to run some queries on a sample dataset loaded into MySQL Database Service and compare the execution times with and without Heatwave. Prepare yourself to be surprised! 
 

![](./images/Intro.png)


**Key Objectives:**

-	Learn how to deploy MySQL Database Service (MDS) DB System with HeatWave 
-	Learn how to enable an HeatWave cluster to MDS DB System
-	Learn how to import data into MDS from an external data source
-	Understand how tables are loaded to HeatWave
-	Learn how to run queries on MDS leveraging or not HeatWave


**Prerequisites:**
-  This workshop requires an Oracle Public Cloud account. You may use a paid cloud account or a trial cloud account.
-  A Cloud tenancy where you have a compartment provisioned in.
  

# Workshop Overview
 
 **All set? Let's start**

## Lab 1 - Create a Virtual Cloud Network and allow traffic through MySQL Database Service port

**Key Objectives:**
 
-	Learn how to create a Virtual Cloud Network with internet connectivity
-	Add ingress rules in the security list to allow traffic through MySQL Database Service ports

**[Click here for Lab 1](./Lab1.md)**

## Lab 2 – Create a compute instance as a bastion host


**Key Objectives:**

-	Learn how to create a compute instance in a specific compartment
 
**[Click here for Lab 2](./Lab2.md)**

## Lab 3 - Create MySQL DB System (MDS) with Heatwave 

**Key Objectives:**

-  Learn how to deploy and configure MySQL Database Service with Heatwave
-  Learn how to create the Administrator user for the MDS

  
**[Click here for Lab 3](./Lab3.md)**

## Lab 4 – Connect to the bastion host, install MySQL Shell and download the workshop dataset

**Key Objectives:**

-  Learn how to connect to the cloud shell and to the bastion host
-  Learn how to launch MySQL shell
-  Download and setup workshop material

**[Click here for Lab 4](./Lab4.md)**

## Lab 5 – Add HeatWave cluster to MySQL Database Service

**Key Objectives:**

-  Learn how to enable the HeatWave cluster for MDS
  
**[Click here for Lab 5](./Lab5.md)**

## Lab 6 – Import data into MDS and load tables to HeatWave

**Key Objectives:**

-  Learn how to connect to MDS and import a dataset 
  
**[Click here for Lab 6](./Lab6.md)**

## Lab 7 – Execute queries leveraging HeatWave

**Key Objectives:**

-  Learn how to enable Heatwave and compare the query execution time with and without HeatWave enabled
  
**[Click here for Lab 7](./Lab7.md)**

## Bonus Lab 8 – Use Analytics Cloud on MySQL Database Service powered by HeatWave

- We wanted to give an additional experience post workshop to learn how to Use Analytics Cloud on MySQL Database Service powered by Heatwave
  
**Key Objectives:**

-  Learn how to use Oracle Analytics Cloud on MySQL Database Service powered by HeatWawe

**[Click here for Lab 8](./Lab8_Bonus_OAC.md)**

## Bonus Lab 9 – Use Data Integration to build your data pipeline with MySQL and HeatWave

- Want to consolidate data from other sources and build your own data pipeline? Even more, do you want to use MySQL and HeatWave for Data Science? This bonus track guide you step by step on how to do it.

**Key Objectives:**
-	Learn how to consolidate data from different sources into MDS and build your own data pipeline
-	Learn how to use MDS powered by HeatWave for your Data Science project by connecting a Jupyter Notebook to MDS

**[Click here for Lab 9](./Lab9_Bonus_DI.md)**