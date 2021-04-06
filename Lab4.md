# Lab 4 - Connect to bastion host, install MySQL Shell and download workshop data

## Introduction


## Key Objectives:
- learn how to connect to bastion host using cloud shell 
- 

## Steps

### **Step 4.1:**
- From the main menu on the left go to _**Compute >> Instances**_
 Click on the instance you have previously created and take note of the _**Public IP Address**_.

![](./images/HW16_ci4.png)

### **Step 4.2:**
- In order to connect to the bastion host, we will use the cloud shell, a small linux terminal embedded in the OCI interface.
To access cloud shell, click on the shell icon next to the name of the OCI region, on the top right corner of the page

![](./images/cloud-shell-1.png)

### **Step 4.3:**
- Once the cloud shell is opened, you will see the command line as per picture below:
  
![](./images/cloud-shell-2.png)

### **Step 4.4**
- We suggest to increase the font size, as per picture below:
  
![](./images/cloud-shell-3.png)

### **Step 4.5:**
- On the top left corner of the cloud shell there are Minimize, Maximize and Close buttons. If you Maximize the cloud shell it will take the size of the entire page. Remember to Restore the size or Minimize prior of changing page in the OCI interface.

![](./images/cloud-shell-4.png)

### **Step 4.6:**
- Drag and drop the previously saved private key into the cloud shell. Get the file name with the command _**ll**_ 
  
![](./images/cloud-shell-5.png)

### **Step 4.7:**
- In order to establish an ssh connection with the bastion host using the Public IP, execute the following commands:
```
chmod 600 <private-key-file-name>.key
ssh -i <private-key-file-name>.key opc@<compute_instance_public_ip>
```

If prompted to accept the finger print, enter _**yes**_ and hit enter.

### **Step 4.8:**
- From the established ssh connection, install MySQL Shell and MySQL client executing the following commands:
```
wget https://dev.mysql.com/get/mysql80-community-release-el7-3.noarch.rpm
sudo yum localinstall mysql80-community-release-el7-3.noarch.rpm
sudo yum install mysql-shell            /*when prompted a warning about the public key enter "y"*/
sudo yum install mysql-community-client
```

### **Step 4.9:**
- Launch MySQL Shell executing the following command:
```
mysqlsh
When you see the MySQL Shell colorful prompt, exit with the following command:
\q
```

### **Step 4.10:**
- Download and unzip the workshop material using the following commands:
```
cd /home/opc
wget https://objectstorage.eu-frankfurt-1.oraclecloud.com/p/wTJ02aU-A5C2RCfBn3ymwm9jaAI01uR23_je6ZnFXMZ3-z3KqZOxpMOMX1zDZvxn/n/odca/b/mysql_data/o/heatwave_workshop.zip
unzip heatwave_workshop.zip
```

### **Step 4.11:**
- Verify the extracted material executing _**ll**_ command.
Among the output, you should see the following file names:
```
tpch_dump
tpch_offload.sql
tpch_queries_mysql.sql
tpch_queries_rapid.sql
```

Now we are connected and the dataset used in the workshop is downloaded, **[Click Here to go to the next lab!](Lab5.md)**
