座学テキストは[コチラ](./xxx.pdf)

# CosmosDBでのベクトル検索 実践編 (Azure Cosmos DB for MongoDB vCore)

### Azure CosmosDB for Mongo DB API vCore
- Mongo DB 互換 API
- VMベースでの提供 = Cosmos DB for PostgreSQLに似ている
> [!TIP]
> RUベースのMongoDB APIとは大きく異なる

## Mongo DB 概要

- [JSON](https://ja.wikipedia.org/wiki/JavaScript_Object_Notation)もしくは[BSON](https://ja.wikipedia.org/wiki/BSON)を保存・抽出できるドキュメントデータベース
- インメモリで高速動作
- データの入出力はAPI(関数)で操作(=SQLは使えない)

|操作|対象|関数|備考|
|---|---|---|---|
|ドキュメントの登録|一件|db.(col).insertOne()||
|ドキュメントの登録|複数|db.(col).insertMany()||
|ドキュメントのクエリ|複数|db.(col).find()||
|ドキュメントの更新|一件|db.(col).updateOne()||
|ドキュメントの更新|複数|db.(col).updateMany()||

- 集計パイプライン

## Cosmos DB for MongoDB vCoreの機能概要

- Mongo DB 互換 NoSQL
- VMベース、性能クラスを選んで利用
- ベクトル関連機能
  - Vector Index (IVFFlat/HNSW)
    - IVFFlat : 反転ファイルフラットインデックス
    - HNSW : 階層化探索可能な小世界
  - Vector Search
    - $Searchの"CosmosSearch"機能で実現 

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

## Cosmos DB for MongoDB vCoreでのベクトルデータの取り扱い

- MongoDB vCoreでのベクトルデータの管理
  
### ベクトルデータの格納

- 環境準備

- サンプルアプリ

- ベクトル生成

### ベクトル検索の実行

- サンプルアプリ

- ベクトル検索
