# HeatWaveを活用した驚異的なパフォーマンスを持つ分析基盤構築

このワークショップでは、Oracle Cloud Infrastructureで分析ワークロードを実行する、もしくはクエリ処理を高速化するためにMySQL Database ServiceとHeatwaveをデプロイするプロセスについて説明します。
 
HeatWaveは、MySQL Database Service(MDS)用に新しく統合された高性能クエリ実行エンジンです。 HeatWaveは、分析クエリ実行のパフォーマンスを400倍高速化し、数千コアにスケールアウトし、Amazon Redshiftの3分の1のコストで2.7倍処理が高速になります。 HeatWaveを備えたMDSは、データベース管理者とアプリ開発者がMySQLデータベースから直接OLTPおよびOLAPワークロードを実行できるようにする唯一のサービスであり、複雑で時間と費用のかかるデータ移動や分析ワークロードと分離する必要性を排除します。</br>
このサービスは、Oracle Cloud Infrastructure（OCI）向けに最適化されています。
 
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
- OCIコンソールの基本操作、およびコンパートメントの作成方法

**[Click here for Lab 0](/Lab0/README.md)**

## Lab 1 - 仮想ネットワークを作成し、MySQL Database Serviceポートへの接続を確立する

**学べること**
 
-	仮想クラウド・ネットワークの作成方法
-	セキュリティリストにイングレスルールを追加してMySQL Database Serviceポートへの接続を確立する

**[Click here for Lab 1](/Lab1/README.md)**

## Lab 2 – Bastionホストとして機能するコンピュートインスタンスを作成する

**学べること**

-	特定のコンパートメントにコンピュート・インスタンスを作成する方法
 
**[Click here for Lab 2](/Lab2/README.md)**

## Lab 3 - MySQL DB System (MDS) および Heatwaveをデプロイする

**学べること**

-  MySQL Database Service および Heatwaveをデプロイし、設定する方法
-  管理者の作成方法

  
**[Click here for Lab 3](/Lab3/README.md)**

## Lab 4 – Bastionホストに接続し、MySQL Shellのインストールとサンプルデータのダウンロード

**学べること**

-  Oracle Cloud Infrastructure (OCI) Cloud ShellとBastionホストへの接続方法
-  MySQL shellの起動方法
-  サンプルデータのダウンロード、およびセットアップ

**[Click here for Lab 4](/Lab4/README.md)**

## Lab 5 – HeatWaveクラスタをMySQL Database Serviceに追加する

**学べること**

-  HeatWaveクラスタを有効にする方法
  
**[Click here for Lab 5](/Lab5/README.md)**

## Lab 6 – MDSへのデータインポートとHeatWaveへのデータロード

**学べること**

-  MDSにデータを格納する方法 
  
**[Click here for Lab 6](/Lab6/README.md)**

## Lab 7 – HeatWaveを有効にしてクエリを実行する

**学べること**

-  HeatWaveを有効にし、HeatWaveが無効になっている場合とクエリ実行時間を比較する
  
**[Click here for Lab 7](/Lab7/README.md)**

## Bonus Lab 8a - OCI Bastion Serviceを利用してMDSをリモートで使う

**学べること**

- リモートでMDSを管理するためのOCI Bastion Serviceの構築方法

**[Click here for Lab 8a](/Lab8a/README.md)**

## Bonus Lab 8b - MDS高可用性構成をデプロイする

**学べること**

- MDS高可用性構成を作成する方法

**[Click here for Lab 8b](/Lab8b/README.md)**

