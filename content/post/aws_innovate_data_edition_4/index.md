---
title: AWS Innovate – Data Edition 見てきました。【その4】

# subtitle: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Summary for listings and search engines
summary: アプリケーションモダナイズの価値とは ～クラウド移行の目的～

# Link this post with a project
# projects: []

# Date published
date: "2021-08-22T00:00:00Z"


# Date updated
lastmod: "2021-08-22T00:00:00Z" 


# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
# image:
#   caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
#   focal_point: ""
#   placement: 2
#   preview_only: false

# authors:
# - admin

tags:
- AWS
- BI

categories:
- AWS
- BI
  
---

AWS Innovate – Data Editionのセッションを聴講した時のメモ その4

リンク元：[AWS Innovate – Data Edition 見てきました。](/post/aws_innovate_data_edition)

## アプリケーションモダナイズの価値とは ～クラウド移行の目的～

|セッション|時間|スピーカー|
|-|-|-|
|T3-3|13:20 - 13:50|アマゾン ウェブ サービス ジャパン株式会社<br/>シニアエバンジェリスト<br/>亀田 治伸 様|

要点
 - データ基盤システムをクラウドに移行すると何が嬉しいのか？
 - データを中心としたモダナイズとは？

### モノリシック分解の重要性

簡素なアプリケーションをAPI連携で有機的に結合させること

何故、データ分析基盤のクラウドネイティブ化が必要か?
 - 多様性の実現、データ分析は総力戦
 - 複数のロールや目的、視点でより多くのユーザーがデータにアクセスし、異なる方法で分析

これがモダナイズの目的

### オンプレミスの問題

クラウド移行により得られるビジネス価値(クラウドエコノミクス)
 - インフラコストの削減(8%)
 - スタッフの生産性(32%)
 - 頑強な オペレーション(13%)
 - 俊敏なビジネス(47%)

→ クラウド移行により得られる価値の90%以上をインフラコスト削減以外の価値が占める

 - オンプレミスでは利用需要に対するインフラコストの最適化が難しい
 - 成功するかわからないものに大きなインフラコストを投資するのはリスクがある

<!-- ### マネージドサービス

ベンダーロックイン??

OSレイヤは抽象化される
1.
2.
3.

マネージドデータベースサービスは1
これはAWS独自じゃない、

123をしっかり分けて考えれば、判断しやすい -->

### レガシーデータベースの制約

有償からOSSに移行すること考えているお客様が多い
 - テクノロジーもロックインされやい
 - ライセンスも高価

しかし...

 - 費用は安いけど、信頼性に不安がある
 - どこかの会社が責任を持つわけではなく、サポートに不安がある
 - そもそもサポートを受けるのも大変

### Amazon Auroraで脱却

 - クラウド向けに構築されたMySQLとPostgreSQL互換のリレーショナル データベース
 - 商用グレードのDBの性能と可用性を1/10のコストで実現

### ReplatformにおけるDBの選択肢と移行

Amazon DMS
 - これまでに300,000のデータベースが移行されている
 - 移行に関するドキュメント(マイグレーションプレイブック)の充実

セットで動作するのがAWS Schema Conversion Tool

### SAP on AWS

SAP
- AWSと強いパートナーシップ
- SAP on AWS 5000ユーザーを超える

SAPとクラウドアーキテクチャをデータで結合
 - アプリケーションレイヤーにSAP
 - データを中心としてAWSの付随するサービスと疎結合型で連携する

### 連携の例：Amazon Forecast with SAP ERP

 - SAP ERP
   - SAP Data を Forecast APIに投入
 - Amazon Forecast
   - 組み込みデータセットを投入
   - 機械学習モデルの自動生成 

データを中心として疎結合型で連携
