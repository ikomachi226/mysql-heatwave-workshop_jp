# Lab 1 - Create VCN and allow MySQL ports

_**1.1 -**_ Log-in to your OCI tenancy. Once you have logged-in, select _**Networking >> Virtual Cloud**_ Networks from the _**hamburger menu**_
![](./images/HW1_vcn.png)

_**1.2 -**_ From the Compartment picker on the bottom right, select your compartment
![](./images/HW1b_vcn.png)

_**1.3 -**_ In the main area of the page, click on _**Start VCN Wizard**_
![](./images/HW2_vcn.png)

_**1.4 -**_ Select _**VCN with Internet Connectivity**_ and click _**Start VCN Wizard**_
![](./images/HW3_vcn.png)

_**1.5 -**_ In the _**VCN NAME**_ field enter the value _**analytics_vcn_test**_ (or any name at your convenience), and make sure that the selected compartment is the right one. Leave all the rest as per default. Click next.
![](./images/HW4_vcn.png)

_**1.6 -**_ Review and click _**Create**_
![](./images/HW5_vcn.png)

_**1.7 -**_ Once the VCN will be created click _**View Virtual Cloud Network**_
![](./images/HW6_vcn.png)

_**1.8 -**_ Click on the _**Public_Subnet-analytics_vcn_test**_ link
![](./images/HW7_vcn.png)

_**1.9 -**_ Click on _**Default_Security_List_for_analytics_vcn_test**_
![](./images/HW8_vcn.png)

_**1.10 -**_ Click on _**Add Ingress Rules**_
![](./images/HW9_vcn.png)

_**1.11 -**_ Follow the instructions on the below image to add the port 3306.
Click _**+ Another Ingress Rule**_ and repeat for port 33060
At the end click the blue button _**Add Ingress Rules**_
![](./images/HW10_vcn.png)

