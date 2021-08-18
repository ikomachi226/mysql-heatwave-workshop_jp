# Lab 0: Sign up a Trial account on Oracle Cloud Infrastructure

## Key Objectives:

- Learn how to sign up a Trial Account on Oracle Cloud Infrastructure

## Introduction

You can sign a Trial account on Oracle Cloud Infrastructure to try out our cloud services such as MySQL Database Services and HeatWave. You will be given free credit of US$300 for 30 days, your trial account will be converted to always-free tier once you have used up all your free credit or 30 days are up

## Steps

## Step - 1: Register to Oracle Cloud to use FREE TIER

**Watch this video for easy reference**: https://www.linkedin.com/feed/update/urn:li:activity:6724226562507595776/
1. To Sign in for an Oracle Cloud Free Tier Account, please, visit https://www.oracle.com/cloud/free/, and click on **Start for free**. </br>
![Image of picture1](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture1.png)
![](./images/Picture1.png)
</br>

2. On Create Account, enter Email Address and Country/Territory, read Terms of Use, and click on **Next** 
![Image of picture2](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture2.png)
</br>

3. On Enter Account Details, select the Account Type, enter Cloud Account Name, First Name, Last Name, Address, City, State, Zip/Postal Code, Country/Territory, and Mobile Number, select the Home Region, and click on **Next: Verify Mobile Number**. </br>
   **Note: You must have an OCI tenancy subscribed to the Tokyo (East)** </br>
![Image of picture3](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture3.png)
</br>

![Image of picture3](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture4.png)
</br>

4.	On Verify Your Mobile Number, enter Code and click on **Verify Code**. 
![Image of picture4](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture5.png)
</br>

5.	On Enter Password, create a Password to be used on the Account.
![Image of picture5](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture6.png)
</br>

6.	On Payment Information, click on Add Credit Card Details. 
![Image of picture6](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture7.png)
</br>

7.	On Payment Method, enter First Name, Last Name, Address, City, Country/Region, State/Province, Zip/Postal Code, Phone Number, Email, Payment Details (including Card Type, Card Number, Expiration Date, CVN), and click on **Finish**.
![Image of picture7](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture8.png)
</br>

![Image of picture7](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture9.png)
</br>

8.	On Payment Information, it will show a message saying **“You won’t be charged unless you elect to upgrade the account.”**. 
**Check the Checkbox to agree to the terms and conditions and click on Complete Sign-Up** 
![Image of picture8](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture10.png)
</br>

9. The Account will be created </br>
![Image of picture1](https://github.com/tripplea-sg/Cloud_Administration_Workshop/blob/main/Lab-1/Picture11.png)


### **Step 1.1:**
  Log-in to your OCI tenancy. Once you have logged-in, select _**Networking >> Virtual Cloud Networks**_ from the _**menu icon**_ on the top left corner

![](./images/HW1_vcn.png)

### **Step 1.2:**
 From the Compartment picker on the bottom left side, select your compartment from the list

![](./images/HW1b_vcn.png)

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

**[Home](../README.md)** | **[Go to Lab 1 >>](../Lab2/README.md)**
