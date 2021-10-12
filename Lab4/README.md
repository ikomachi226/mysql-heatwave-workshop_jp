# Lab 4: Bastionへの接続、MySQL Shellのインストールとサンプルデータのダウンロード

## 実施すること
- Oracle Cloud Infrastructure (OCI) Cloud ShellとBastionホストへの接続方法を学ぶ
- MySQL shellの起動方法を学ぶ
- サンプルデータのダウンロード、およびセットアップ
  
## 概要

Oracle Cloud Infrastructure (OCI) Cloud Shellは、OCIコンソールからアクセスしBashシェルを実行する小さな仮想マシンです。 Cloud Shellには、テナンシーのホームリージョンに設定された事前認証済みのOCI CLIと、最新のツールおよびユーティリティが付属しています。Cloud Shellには、ホームディレクトリ用に5GBの永続ストレージが付属しているため、ホーム・ディレクトリにローカルで変更を加えた後、クラウド・シェルに戻ったときにプロジェクトで作業を続行できます。クラウド・シェルは(月次テナンシ制限内で)無償で使用でき、クラウド・シェルへのアクセス権を付与するIAMポリシー以外の設定または前提条件が必要ありません。クラウド・シェルには、それ自体のテナンシで実行されるVMがプロビジョニングされています(テナンシのリソースが使用されないため)。

## 手順

### **Step 4.1:**
- 画面左上のメニューから _**コンピュート >> インスタンス**_ を選択します。
 作成済のインスタンスをクリックして _**パブリックIPアドレス**_ をコピーします。

![](./images/HW16_ci4.png)

### **Step 4.2:**
- Bastionホストに接続するためにOCIコンソールに付属しているLinuxターミナルであるCloud Shellを利用します。
　Cloud Shellにアクセスするために, 画面右上に表示されているOCIリージョンの右側に表示されているCloud Shellアイコンをクリックします。
![](./images/cloud-shell-1.png)

### **Step 4.3:**
- Cloud Shellを起動すると、下記画面例のようなターミナルが表示されます。
  
![](./images/cloud-shell-2.png)

### **Step 4.4**
- 操作しやすくする為に、ここでフォントサイズを変更することを推奨します。
  
![](./images/cloud-shell-3.png)

### **Step 4.5:**
- Cloud Shellウィンドウの右上隅には、[最小化]、[最大化]、[終了]ボタンがあります。 クラウドシェルを最大化すると、ページ全体のサイズになります。 OCIコンソールのページを移動する前に、サイズを元に戻すか最小化することを忘れないでください。

![](./images/cloud-shell-4.png)

### **Step 4.6:**
- 保存してある秘密キーをCloud Shellウィンドウにドラッグ・アンド・ドロップします。_**ll**_ コマンドでファイル名を取得します。
  
![](./images/cloud-shell-5.png)

### **Step 4.7:**
- パブリックIPアドレスを用いてBastionホストとSSH接続を確立させるため、以下のコマンドを実行します。
```
chmod 600 <private-key-file-name>.key
ssh -i <private-key-file-name>.key opc@<compute_instance_public_ip>
```

フィンガープリントを受け入れるかどうか確認されたら、 _**yes**_ と入力し、Enterキーを押すと以下の様な警告が表示されます。

_**Warning: Permanently added '130.******' (ECDSA) to the list of known hosts.**_

ここまでの操作でインスタンスに接続できるようになりました。

### **Step 4.8:**
- 次のコマンドを実行してMySQL ShellとMySQLクライアントをインストールします。 
  
```
wget https://dev.mysql.com/get/mysql80-community-release-el7-3.noarch.rpm
```
![](./images/cloud-shell-6.png)
```
sudo yum localinstall mysql80-community-release-el7-3.noarch.rpm
```
![](./images/cloud-shell-7.png)

_**公開キーについて警告が表示された場合は "y"を入力します**_ 

```
sudo yum install mysql-shell  
```
![](./images/cloud-shell-8.png)

_**公開キーについて警告が表示された場合は "y"を入力します

```
sudo yum install mysql-community-client
```

![](./images/cloud-shell-9.png)

_**公開キーについて警告が表示された場合は "y"を入力します**_


### **Step 4.9:**
- 以下のコマンドを実行し、MySQL Shellを起動します。
```
mysqlsh
```
MySQL Shellプロンプトが表示されたら、以下のコマンドを実行して終了します。
```
\q
```

### **Step 4.10:**
- 以下のコマンドを実行して、演習用資材をダウンロード、解凍します。
```
cd /home/opc
```

```
wget https://objectstorage.eu-frankfurt-1.oraclecloud.com/p/wRGvQM7cJAXu6_YoMIfzLeWQnnw5zUXlSOynelMlADOFfQI3t1ugdRB7U8fFnFHG/n/odca/b/MySQL_Data/o/heatwave_workshop.zip
```

![](./images/cloud-shell-10.png)

```
unzip heatwave_workshop.zip
```

![](./images/cloud-shell-11.png)


解凍できたら次の手順に進みます。

### **Step 4.11:**
- _**ll**_ コマンドを実行して展開された資材を確認します。
以下のファイルが含まれています。

_**tpch_dump**_

_**tpch_offload.sql**_

_**tpch_queries_mysql.sql**_

_**tpch_queries_rapid.sql**_

![](./images/cloud-shell-12.png)


## まとめ

ここまでの操作で、Cloud Shellの起動、コンピュート・インスタンスに接続するための秘密キーをインポートしました。 更に、MySQL ShellとMySQLクライアントをインストールし、最後に後でベンチマークに使用する資材をダウンロードして解凍しました。

**[<< Lab 3](/Lab3/README.md)** | **[Home](../README.md)** | **[Lab 4a >>](/Lab4a/README.md)**
