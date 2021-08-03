# Lab 8a: Use OCI Bastion Service to work with MDS remotely

## Key Objectives:

- Learn how to create OCI Bastion Service to manage MDS remotely

## Introduction

Oracle Cloud Infrastructure (OCI) Bastion provides restricted and time-limited access to target resources that don't have public endpoints. With OCI Bastion Service, you can
manage MDS instance via secured connection remotely using OCI Bastion Service
For an overview of OCI Bastion Service, check **[OCI Bastion Service](https://docs.oracle.com/en-us/iaas/Content/Bastion/Concepts/bastionoverview.htm)**.

## Steps

### **Step 1.1:**
  Log-in to your OCI tenancy. Once you have logged-in, select _**Database >> MySQL >> DB Systems**_ from the _**menu icon**_ on the top left corner
  
![](./images/Bas-1.png)

### **Step 1.2:**
 Click on _**Create MySQL DB Systems**_

![](./images/Bas-2.png)

### **Step 1.3:** 
 To create a virtual cloud network, click on _**Start VCN Wizard**_ , 
  
![](./images/HW2_vcn.png)

### **Step 1.4:** 
 Select _**VCN with Internet Connectivity**_ and click _**Start VCN Wizard**_

![](./images/HW3_vcn.png)

### **Step 1.5:**
 Now you need to complete some information and set the configuration for the VCN. In the _**VCN NAME**_ field enter the value _**analytics_vcn_test**_ (or any name at your convenience), and make sure that the selected compartment is the right one. Leave all the rest as per default. Click next.

![](./images/HW4_vcn.png)

### **Step 1.6:** 
 Review and click _**Create**_

![](./images/HW5_vcn.png)

### **Step 1.7:** 
 Once the VCN will be created click _**View Virtual Cloud Network**_

![](./images/HW6_vcn.png)

### **Step 1.8:** 
 Click on the _**Public_Subnet-analytics_vcn_test**_ link. 

![](./images/HW7_vcn.png)

### **Step 1.9:** 
 Earlier we set up the subnet to use the VCN's default security list, that has default rules, which are designed to make it easy to get started with Oracle Cloud Infrastructure. 
 Now we will customize the default security list of the VCN to allow traffic through MySQL Database Service ports by clicking on  _**Default_Security_List_for_analytics_vcn_test**_

![](./images/HW8_vcn.png)

### **Step 1.10:** 
  Click on _**Add Ingress Rules**_

![](./images/HW9_vcn.png)

### **Step 1.11:**
 Add the necessary rule to the default security list to enable traffic through MySQL Database Service port. 

Insert the details as below:
Source CIDR  _**0.0.0.0/0**_,  port _**3306**_, description  _**MySQL Port**_.

At the end click the blue button _**Add Ingress Rules**_

![](./images/HW10_vcn.png)


## Conclusion

Now that you have created the VCN and added the additional Ingress rules to the Security list, you can proceed to the next lab!

Learn more about **[VCN and Subnets](https://docs.oracle.com/en-us/iaas/Content/Network/Tasks/managingVCNs_topic-Overview_of_VCNs_and_Subnets.htm)**

**[Home](../README.md)** | **[Go to Lab 2 >>](../Lab2/README.md)**
