# HeatWaveを活用した驚異的なパフォーマンスを持つ分析基盤構築

このワークショップでは、Oracle Cloud Infrastructureで分析ワークロードを実行する、もしくはクエリ処理を高速化するためにMySQL Database ServiceとHeatwaveをデプロイするプロセスについて説明します。
 
HeatWaveは、MySQL Database Service(MDS)用に新しく統合された高性能クエリ実行エンジンです。 HeatWaveは、分析クエリ実行のパフォーマンスを400倍高速化し、数千コアにスケールアウトし、Amazon Redshiftの3分の1のコストで2.7倍処理が高速になります。 HeatWaveを備えたMDSは、データベース管理者とアプリ開発者がMySQLデータベースから直接OLTPおよびOLAPワークロードを実行できるようにする唯一のサービスであり、複雑で時間と費用のかかるデータ移動や分析ワークロードと分離する必要性を排除します。このサービスは、Oracle Cloud Infrastructure（OCI）向けに最適化されています。
 
ハンズオンを進めるとMDSにロードされたサンプルデータに対してクエリを実行し、Heatwaveを利用する場合と利用しない場合の実行時間の比較ができるようになります。HeatWaveの性能を体感してください！

![](./images/Intro.png)


**学べること**

-	MySQL Database Service (MDS) および HeatWaveのデプロイ
-	HeatWaveクラスタを有効にする方法
-	MDSへのデータ格納
-	HeatWaveへのテーブルロード
-	HeatWaveを利用したクエリ実行方法


**前提条件**
-  このハンズオンでは、Oracle Cloud Infrastructureのアカウントが必要になります。有償アカウント、もしくはトライアルアカウントをご用意ください。
-  コンパートメントが作成されたテナンシが必要になります。
  

# ハンズオン概要
 
 **準備ができたら始めましょう**
 
## Lab 0 - Oracle Cloud Infrastructureのトライアルアカウントを作成する

**学べること**

- トライアルアカウントの作成方法
- 適切なリージョンの選択

**[Go to Lab 0](/Lab0/README.md)**

## Lab 1 - Create a Virtual Cloud Network and allow traffic through MySQL Database Service port

**Key Objectives:**
 
-	Learn how to create a Virtual Cloud Network with internet connectivity
-	Add ingress rules in the security list to allow traffic through MySQL Database Service ports

**[Click here for Lab 1](/Lab1/README.md)**

## Lab 2 – Create a compute instance as a bastion host


**Key Objectives:**

-	Learn how to create a compute instance in a specific compartment
 
**[Click here for Lab 2](/Lab2/README.md)**

## Lab 3 - Create MySQL DB System (MDS) with Heatwave 

**Key Objectives:**

-  Learn how to deploy and configure MySQL Database Service with Heatwave
-  Learn how to create the Administrator user for the MDS

  
**[Click here for Lab 3](/Lab3/README.md)**

## Lab 4 – Connect to the bastion host, install MySQL Shell and download the workshop dataset

**Key Objectives:**

-  Learn how to connect to the cloud shell and to the bastion host
-  Learn how to launch MySQL shell
-  Download and setup workshop material

**[Click here for Lab 4](/Lab4/README.md)**

## Lab 4a – Create a compute instance, install mysqlrouter for Oracle Analytics Cloud

**Key Objectives:**

-  Learn how to install mysqlrouter 
-  Learn how to configure mysqlrouter to allow Oracle Analytics Cloud to connect to MDS/HeatWave

**[Click here for Lab 4a](/Lab4a/README.md)**

## Lab 5 – Add HeatWave cluster to MySQL Database Service

**Key Objectives:**

-  Learn how to enable the HeatWave cluster for MDS
  
**[Click here for Lab 5](/Lab5/README.md)**

## Lab 6 – Import data into MDS and load tables to HeatWave

**Key Objectives:**

-  Learn how to connect to MDS and import a dataset 
  
**[Click here for Lab 6](/Lab6/README.md)**

## Lab 7 – Execute queries leveraging HeatWave

**Key Objectives:**

-  Learn how to enable Heatwave and compare the query execution time with and without HeatWave enabled
  
**[Click here for Lab 7](/Lab7/README.md)**

## Bonus Lab 8a - Use OCI Bastion Service to manage MDS

**Key Objectives:**

- Learn how to use the free OCI Bastion Service to manage MDS remotely

**[Click here for Lab 8a](/Lab8a/README.md)**

## Bonus Lab 8b - Deploy your mission critical application on MDS High Availability

**Key Objectives:**

- Learn how to provision MDS with High Availability enabled for your mission-critical application

**[Click here for Lab 8b](/Lab8b/README.md)**

