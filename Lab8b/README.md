# Lab 8b: MDS高可用性構成を利用してミッションクリティカルアプリケーションを運用する

## Key Objectives:

- MDS高可用性構成を作成・セットアップする方法を学ぶ

## Introduction

MDSは、データ損失をゼロにすることを要求するミッションクリティカルなアプリケーションに _**高可用性**_ を提供します。MDS 高可用性構成には、異なるアベイラビリティ。ドメインまたはフォルト・ドメインにデプロイされた3つのMySQLインスタンスが含まれています。 データは、MySQLグループレプリケーションを使用してレプリケートされます。 アプリケーションは単一のエンドポイントに接続して、データベースのデータ読み取りと書き込みを行います。 障害が発生した場合、DBシステムは、アプリケーションの再構成を必要とせずに、セカンダリインスタンスに自動的にフェイルオーバーします。
MDS高可用性構成の概要については、**[高可用性](https://docs.oracle.com/ja-jp/iaas/mysql-database/doc/business-continuity.html#MYAAS-GUID-2CD8BFB9-30B2-4ED5-BE27-E526DD3F6E0A)** をご参照ください。

## Steps

### **Step 1.1:**
  OCIコンソール左上のメニューから _**データベース >> MySQL >> DBシステム*_ を選択します。
  
![](./images/ha-1.png)

### **Step 1.2:**
 _**MySQL DBシステムの作成**_ をクリックします。

![](./images/ha-2.png)

### **Step 1.3:** 
 _**高可用性**_ を選択し、各項目を入力します。
 * _**コンパートメントに作成**_: 適切なコンパートメント
 * _**名前**_: MDSインスタンの名前 (例: MDS_HA)
 * _**説明**_: MDSインスタンス利用用途などの説明
 * _**ユーザー名**_: MDSの管理者(例： admin)
 * _**パスワード**_: 管理者パスワード

![](./images/ha-3.png)

### **Step 1.3:** 
 _**仮想クラウド・ネットワーク**_ を選択します。(デフォルトでは、仮想クラウド・ネットワークのプライベート・サブネットが設定されています)
 
 ![](./images/ha-4.png)

### **Step 1.4:**
 Click on _**Create**_ to create the MDS High Availabilty configuration, you should be able to use MDS HA in a few minutes once it is provisioned. Enjoy!
 
 ![](./images/ha-5.png)
 
## Conclusion

Congratulations! You have completed the 2 bonus labs. 

**[<< Go to Lab 8a](/Lab6/README.md)** | **[Home](../README.md)** 


