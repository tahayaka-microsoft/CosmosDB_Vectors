座学テキストは[コチラ](./xxx.pdf)

# CosmosDBでのベクトル検索 実践編 (Azure Cosmos DB for MongoDB vCore)

### Azure CosmosDB for Mongo DB API vCore
- Mongo DB 互換 API
- VMベースでの提供 = Cosmos DB for PostgreSQLに似ている
> [!TIP]
> RUベースのMongoDB APIとは大きく異なる

## Mongo DB 概要

- JSONもしくはBSON(Binary形式)を保存・抽出するドキュメントデータベース
- インメモリで高速動作
- データの入出力はAPI(関数)で操作
- 集計パイプライン

## Cosmos DB for MongoDB vCoreの機能概要

- Mongo DB 互換 NoSQL
- Vector Index (IVFFlat/HNSW)
- Vector Search 

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
