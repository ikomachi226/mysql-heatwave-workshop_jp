# Lab 1: Create VCN and allow MySQL ports

## Introduction

Virtual Cloud Network helps you define your own data centre network topology inside the Oracle Cloud, by defining some of the following components (Subnets, Route Tables, Security Lists, Gateways, etc.)

## Key Objectives:

- Learn how to create a Virtual Cloud Network 

## Required Artifacts

- The following lab requires an Oracle Public Cloud account. You may use your own cloud account, a cloud account that you obtained through a trial, or a training account whose details were given to you by an Oracle instructor.

## Steps

### **Step 1.1:**
 Log-in to your OCI tenancy. Once you have logged-in, select _**Networking >> Virtual Cloud Networks**_ from the _**hamburger menu**_

![](./images/HW1_vcn.png)

### **Step 1.2:**
 From the Compartment picker on the bottom right, select your compartment

![](./images/HW1b_vcn.png)

### **Step 1.3:** 
 In the main area of the page, click on _**Start VCN Wizard**_
![](./images/HW2_vcn.png)

### **Step 1.4:** 
 Select _**VCN with Internet Connectivity**_ and click _**Start VCN Wizard**_

![](./images/HW3_vcn.png)

### **Step 1.5:**
 In the _**VCN NAME**_ field enter the value _**analytics_vcn_test**_ (or any name at your convenience), and make sure that the selected compartment is the right one. Leave all the rest as per default. Click next.

![](./images/HW4_vcn.png)

### **Step 1.6:** 
 Review and click _**Create**_

![](./images/HW5_vcn.png)

### **Step 1.7:** 
 Once the VCN will be created click _**View Virtual Cloud Network**_

![](./images/HW6_vcn.png)

### **Step 1.8:** 
 Click on the _**Public_Subnet-analytics_vcn_test**_ link

![](./images/HW7_vcn.png)

### **Step 1.9:** 
 Click on _**Default_Security_List_for_analytics_vcn_test**_

![](./images/HW8_vcn.png)

### **Step 1.10:** 
 Click on _**Add Ingress Rules**_

![](./images/HW9_vcn.png)

### **Step 1.11:**
 Follow the instructions on the below image to add the port 3306.
Click _**+ Another Ingress Rule**_ and repeat for port 33060
At the end click the blue button _**Add Ingress Rules**_

![](./images/HW10_vcn.png)


**[Go to the next Lab](Lab2.md)**
