# Lab 3 - Create MySQL DB System (MDS) for Heatwave

_**3.1 -**_ From the main menu on the left select _**MySQL >> DB System**_
![](./images/HW17_mds.png)

_**3.2 -**_ The previous step will bring you to the DB System creation page. 
Look at the compartment selector on the left and check that you are using the same compartment used to create the VCN and the Compute Instance. Once done, click on Create MySQL DB System.
![](./images/HW18_mds.png)

_**3.3 -**_ Start creating the DB System. Cross check again the compartment and assign to the DB System the name _**mysql-analytics-test**_ and select the HeatWave box. This will allow to create a MySQL DB System which will be HeatWave-ready. Ignore other boxes.
![](./images/HW19_mds.png)

_**3.4 -**_ In the _**Create Administrator Credential**_ section enter the following:
username: admin
password: Oracle.123
In the _**Configure Networking**_ section make sure you select the same subnet which you have used to create the Compute Instance (Public-Subnet-analytics_vcn_test).
![](./images/HW20_mds.png)

_**3.5 -**_ Leave the default availability domain and proceed to the _**Configure Hardware**_ section.
![](./images/HW21_mds.png)

_**3.6 -**_ Confirm that in the _**Configure Hardware**_ section, the selected shape is MySQL.HeatWave.VM.Standard.E3, CPU Core Count: 16, Memory Size: 512 GB, Data Storage Size: 1024.
In the _**Configure Backup**_ section leave the default backup window of 7 days.
![](./images/HW22_mds.png)

_**3.7 -**_ Scroll down and click on _**Show Advanced Options**_ 
![](./images/HW23_mds.png)

_**3.8 -**_ In the Configuration tab click on _**Select Configuration**_ 
![](./images/HW24_mds.png)

_**3.9 -**_ In the _**Browse All Configurations**_ window, select MySQL.HeatWave.VM.Standard.E3.Standalone, and click the button _**Select a Configuration**_ 
![](./images/HW25_mds.png)

_**3.10 -**_ If everything is correct you should see something corresponding to the below
![](./images/HW26_mds.png)

_**3.11 -**_ Go to the Networking tab, and in the Hostname field enter _**mysql-analytics-test**_ (same as DB System Name). 
Check that port configuration corresponds to the following:
MySQL Port: 3306
MySQL X Protocol Port: 33060
Once done, click the _**Create**_ button.
![](./images/HW27_mds.png)

_**3.12 -**_ The MySQL DB System will enter _**CREATING**_ state (as per picture below). Do not wait for completion and go to the next excercise.
![](./images/HW28_mds.png)

**[Go to the next Lab](Lab4.md)**
