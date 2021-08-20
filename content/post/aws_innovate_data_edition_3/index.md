---
title: AWS Innovate – Data Edition 見てきました。【その3】

# subtitle: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Summary for listings and search engines
summary: 転職サービスにおけるデータ分析基盤の構築事例

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

AWS Innovate – Data Editionのセッションを聴講した時のメモ その3

リンク元：[AWS Innovate – Data Edition 見てきました。](/post/aws_innovate_data_edition)

## 転職サービスにおけるデータ分析基盤の構築事例

|セッション|時間|スピーカー|
|-|-|-|
|CUS1-2<br/>お客様事例|12:40 - 13:10|ミイダス株式会社 CTO<br>大谷 祐司 様|

### ミイダスの事業

 - スカウト型の転職サービス
 - 求職者、採用企業のデータを元にお互いにマッチした適材適所を採用を実現

### ミイダスのインフラとデータベース

メインDBはAmazon Aurora(MySQL)

用途によって細かくインスタンスを使い分けている
 - メインのWriter、
 - フェイルオーバー用Reader
 - 用途別の小型Reader

転職サービスにおけるデータの特徴
 - 求職者と企業の掛け算でデータが増加していく(現在数十億件)
 - スカウトデータは、頻繁にデータの洗い替えが必要になる
 - メール通知などのバッチ処理が多く、終了必須の時間がシビアに決まっている

|複数のデータベースを組み合わせ、それぞれの特性を活かした運用を実施||
|-|-|
|求人情報など、全文検索されるテキストデータ|Amazon CloudSearch|
|頻繁に洗い替えが必要なスカウト情報など|Amazon ElastiCache|
|求職者に紐づいた、画面表示用の求人情報など|Amazon DocumentDB|

### データ分析で抱えていた課題

従来は、AuroraのReaderを基盤として活用

 - 構築した当初はサービスの規模が小さかった
 - エンジニアが分析できれば良いというコンセプトだった

しかし、

 - SQLベースで抽出するのでデータ容量が増えるとパフォーマンスの悪化が見られた
 - 当初はそれでも良かったが、将来的にサービスが成長するにはデータ分析基盤の構築が不可欠だった

<span style="font-weight: bold;">→ ミイダスにとって、データ分析は将来に向けて非常に重要であると位置づけ、 AWS上にデータ分析基盤を構築することを意思決定する。</span>

### データ分析基盤構築の要件

 - 運用の手間を減らし、分析者が業務に集中できる環境にしたい
 - 将来的なサービスの成長に合わせて、データが増えた際にもインフラをスケールさせたい
 - 開発者以外も気軽に利用できる環境を構築したい
   - Webベースのインターフェイスを作って利用できるようにしたい


### 構成

 - メインのデータ保存先(データレイク)はS3を採用
   - AWS Database Migration Service (DMS)でAmazon Aurora のデータをコピー
 - 可視化・分析はQuickSightを活用
   - Amazon RedShiftに蓄積されたデータをGUIで簡単に操作

### 選定のポイント

#### AWS DMS

AuroraのデータをS3にコピーする際に利用
 - 対障害耐性などの信頼性が高く、Auroraの処理に影響を与えずデータコピーできる
 - 大容量のデータの迅速なマイグレーションもサポートしている
 - きっかけはハンズオンだった

#### AWS Glue
 - サーバレスで手軽に利用できる。フォーマットの柔軟性が高く、データの変更に強い。

用途
 - S3 に蓄積されているデータについて、MySQLの型をPostgreSQLの型に変換
 - DBやアクセスログのデータから個人情報をマスク
 - Amazon Redshift へデータをLoad

#### RedshiftとQuickSightの組み合わせ
 - 優れたUIとパフォーマンス
 - 従来行っていたSQLでのデータ分析と比較して、数10-数100倍のパフォーマンスUPを実現

### データ分析基盤の構築による影響

開発以外の部門も含めた組織にとって良い効果があった
 - マーケティングなどの人が自分でデータに興味を持ってどんどん分析して深掘りするようになった
 - エンジニアに依頼しなくても自分で触って分析できる

エンジニアチームに起こった変化
 - データ分析基盤の運用に時間を取られなくなった
 - GUIによるインターフェースによって、従来の高度なSQLによるデータ抽出に比べて大幅に工数が削減できた

