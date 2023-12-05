座学テキストは[コチラ](./xxx.pdf)

# CosmosDBでのベクトル検索 実践編 <BR> (Azure Cosmos DB for MongoDB vCore)

## Mongo DB 概要

- [JSON](https://ja.wikipedia.org/wiki/JavaScript_Object_Notation)もしくは[BSON](https://ja.wikipedia.org/wiki/BSON)を保存・抽出できるドキュメントデータベース&NoSQLデータストア
- インメモリで高速動作
- データの入出力はAPI(関数)で操作(=SQLは使えない)
- 並列処理対応
- 集計パイプラインによるわかりやすい集計・データ処理記述

## Cosmos DBファミリーでのMongoDB API

### Mongo DB API (RUベース)

- CosmosDB for NoSQLと同一のアーキテクチャーを持つ
- データの読み書きに関してはMongoDBの関数が利用できる(互換性が高い)
- RUの増減で処理キャパシティが変わる。オーバー分はHTTP429が返る。
- 内部的にはマスター以外に3つのレプリカを持つため可用性が高い
- プロビジョニングされたRUとストレージの合算

### Mongo DB vCore (vCoreベース)

- CosmosDB for PostgreSQLのように、ノードをデプロイして利用する
- 基本1node。処理に応じてもう1node足すことができる(将来的にはさらに足せるようになる。。。かも)
- サーバークラス(Tier)を指定してデプロイする。サーバークラスは以下から選択。

|クラス|vCore|メモリ|時間あたり単価(東日本)|
|---|---|---|---|
|M25|2(Burst可)|8GB|$0.222/h|
|M30|2|8GB|$0.303/h|
|M40|4|16GB|$0.605/h|
|M50|8|32GB|$1.209/h|
|M60|16|64GB|$2.418/h|
|M80|32|128GB|$4.836/h|
|M200|64|256GB|$9.671/h|
|M300|96|384GB|$14.506/h|

- ストレージは以下の中から選択。プロビジョニング(確保した)分について月単位の課金となる。

|サイズ|料金|
|---|---|
|64GB|$8.832/月|
|128GB|$17.664/月|
|256GB|$35.328/月|
|512GB|$70.656/月|
|1,024GB|$141.312/月|
|2,048GB|$282.624/月|

- HA(高可用性)にすると単純に料金が倍
- ストレージとコンピュートの合算

## Cosmos DB for MongoDB vCoreの機能概要

- Mongo DB **互換** NoSQL (v5.0相当)
- VMベース。性能クラスを選んで利用 (M20~M100)
- コンピュート時間とストレージ容量で課金(RUとは異なる)
- コンピュート・メモリがノード単位で確保されており、計算量があってもエラーにならない
- ベクトル関連機能
  - Vector Index (IVFFlat/HNSW)
    - IVFFlat : 反転ファイルフラットインデックス
    - HNSW : 階層化探索可能な小世界
  - Vector Search
    - $Searchの"cosmosSearch"機能で実現 

## Cosmos DB for MongoDB vCoreのサービス作成

- Azure Portalからサービスの作成

## Cosmos DB for MongoDB vCoreの基本操作

- mongoshインストール
- mongoshでの操作
  - 接続
  - データベース操作
  - コレクション操作
  - アイテム操作
  - 集計パイプライン操作
 
- Pythonでの操作
  - 利用するパッケージ(motor)のインストール
  - 接続
  - データベース操作
  - コレクション操作
  - アイテム操作
  - 集計パイプライン操作

## Cosmos DB for MongoDB vCoreでのベクトルデータの取り扱い

- MongoDB vCoreでのベクトルデータの管理
  
### ベクトルデータの格納

- 環境準備

- サンプルアプリ

- ベクトル生成

### ベクトル検索の実行

- サンプルアプリ

- ベクトル検索

<!--
墓場
|操作|対象|mongosh|python(Motor)|備考|
|---|---|---|---|---|
|ドキュメントの登録|一件|db.(col).insertOne()|||
|ドキュメントの登録|複数|db.(col).insertMany()|||
|ドキュメントのクエリ|複数|db.(col).find()|||
|ドキュメントの更新|一件|db.(col).updateOne()|||
|ドキュメントの更新|複数|db.(col).updateMany()|||
-->
