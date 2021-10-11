# Lab 1: 仮想ネットワークを作成し、MySQL Database Serviceポートへの接続を確立する

## 実施すること:

- インターネット接続を持つ仮想ネットワーク(VCN)の作り方を学ぶ
- セキュリティリストにイングレスルールを追加してMySQL Database Serviceポートへの接続を確立する


## 概要

VCNは、サブネット、ルートテーブル、セキュリティリスト、ゲートウェイなどを定義することにより、OracleCloud内で独自のデータセンターネットワークトポロジを設定することができます。これらのコンポーネントの一部は、すべてのVCN内でデフォルトで自動的に設定され削除することはできません。
•	ルート・ルールのないデフォルトのルート表
•	デフォルトのセキュリティ・ルールが設定されたデフォルトのセキュリティリスト
•	デフォルト値のあるDHCPオプションのデフォルト・セット
VCNの概要、許容サイズ、デフォルトのVCN、およびVCNを使用するためのシナリオについては **[ネットワークの概要](https://docs.oracle.com/en-us/iaas/Content/Network/Concepts/overview.htm#network_landing)** を確認してください。

セキュリティリストは、インスタンスの仮想ファイアウォールとして機能し、出入りを許可するトラフィックのタイプを指定するイングレスルールとエグレスルールを備えています。各サブネットには複数のセキュリティリストを関連付けることができ、各リストには複数のルールを含めることができます。デフォルトのセキュリティリストには、ステートフル・ルールの初期セットが付属しています。ほとんどの場合、そのVCNまたはサブネットをホストするリージョンに関連する許可されたサブネットからのインバウンドトラフィックのみを許可するように変更する必要があります。各リージョンに関連する許可されたサブネット範囲のリストは、**[こちら](https://docs.cloud.oracle.com/iaas/tools/public_ip_ranges.json)** にあります。

## 手順

### **Step 1.1:**
  OCIテナンシにログインし、_**Networking >> Virtual Cloud Networks**_ from the _**menu icon**_ on the top left corner

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

**[Home](../README.md)** | **[Go to Lab 2 >>](../Lab2/README.md)**
