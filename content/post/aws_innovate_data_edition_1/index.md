---
title: AWS Innovate – Data Edition 見てきました。【その1】

# subtitle: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Summary for listings and search engines
summary: AWS のデータ分析サービスの方向性 ～お客様データドリブンビジネスを支える～

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

AWS Innovate – Data Editionのセッションを聴講した時のメモ その1


リンク元：[AWS Innovate – Data Edition 見てきました。](/post/aws_innovate_data_edition)


## AWS のデータ分析サービスの方向性 ～お客様データドリブンビジネスを支える～
|セッション|時間|スピーカー|
|-|-|-|
|KEY-01<br/>オープニングセッション|10:00 - 11:00|アマゾン ウェブ サービス ジャパン株式会社<br/>シニアエバンジェリスト<br/>亀田 治伸 様|

### 新しい生活様式、ワークスタイル

コロナショックによって激増
 - キャッシュレス
 - 家庭でのゲーム、エンタメ
 - フードデリバリーサービス
 - ect...

時代への適合には、クラウドコンピューティングによって、迅速で柔軟にスケールさせることが重要。

### データの爆発

世の中のデータが、より多くより多様に増え続けている。
どのように処理するかが今後のビジネスに重要である。
よりやすく使いやすい形で使いたい。

安定したデータ収集のために
 - Amazon Kinesis
 - Amazon MSK(去年リリース)

#### データは新しい石油?

石油を捻出する精錬作業が我々の生活を支えている。

データ活用の価値は、データ加工・分析を経て有用なものとなるので、データは石油の前段階と言える。

### クラウドの利点をデータ活用の基盤構築で活かす

 - コスト削減
 - システムの柔軟性、俊敏性
 - 開発のスピード

### データレイクアーキテクチャ

 - 機械学習や分析用の解析基盤はストレージより高価である
 - 全ての生のデータは安価でエクサバイトレベルまでスケールするストレージ(S3)に保存しておく
 - 高価な解析基盤は必要な時だけ起動するのが基本コンセプト

### 多様性の実現、データ分析は総力戦

単一のテクノロジーにのみ対応するストレージに格納するのではなく、最も汎用的なストレージに入れることで多種多様な分析基盤の中心を担うことができる。

汎用的なストレージにしておくことでDBだけでなく様々なサービスと連携できるようにする。

<span style="font-weight: bold;">Data grabity</span>

- データを格納した１箇所のストレージに様々なアプリケーションが集まっていく様子。

### Amazon Redshift

 - RA3インスタンス
 - AQUA
 - Elastic Resize
 - Concurrency Scaling
 - Data Sharing

### データレイクの設定、構築、セキュリティ

 - AWS Lake Formation 
   - Amazon Athena
   - Amazon S3
 - AWS Glue
   - Studio
   - DataBrew
   - Elastic Views

### Purpose-built Analytics

目的に応じて最適な分析基盤を構築する。

SQLから機械学習モデルを学習して推論を実行

 - Amazon Redshift ML
 - Amazon Athena ML

Federated query
 - Amazon Redshift
 - Amazon Athena

その他
 - Amazon EMR
 - Amazon Elasticseach Service

### BI - Amazon QuickSight
サーバレスで運用不要のBIサービス

 - ブラウザで全て完結
 - ユーザ数に応じてスケール
 - 他AWSサービスとのシームレスな統合
 - 利用した分だけの費用

Reader権限
 - ライセンスを持っていてもアクセスしなければ課金なし

