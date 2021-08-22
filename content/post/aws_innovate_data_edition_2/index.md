---
title: AWS Innovate – Data Edition 見てきました。【その2】

# subtitle: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Summary for listings and search engines
summary: 30分で学ぶ！中堅・中小企業の方のためのデータ分析はじめの一歩

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

AWS Innovate – Data Editionのセッションを聴講した時のメモ その2


リンク元：[AWS Innovate – Data Edition 見てきました。](/post/aws_innovate_data_edition)

## 30分で学ぶ！中堅・中小企業の方のためのデータ分析はじめの一歩

|セッション|時間|スピーカー|
|-|-|-|
|T3-1|12:00 - 12:30|アマゾン ウェブ サービス ジャパン株式会社 <br/>ソリューションアーキテクト<br/>山澤 良介 様|

### 本セッションについて

対象
 - 既存のデータを活用してデータ分析を始めたい方
 - データ分析に興味はあるけれど、あまりわかっていないんだよね...という方々

よくある課題
 - 情報システム部の人件費が少ない
 - 新しいことにコストがかけられない

### 何故データ分析するのか？

ビズネス課題に対して、データに基づいた意思決定をするため

1. ビジネス課題
2. データ収集
3. 分析
4. 評価
5. 1に戻る

まず最初にやることはビジネス課題を明確にすること
 
### 意思決定に必要な<span style="color: red;">指標</span>

 - 定量的な計測可能なメトリクス
 - メトリクスの元となる大量な生データ
 - 元データを指標に変換する仕組み

指標と元デーやの例

|ビジネス課題|指標|データ|
|-|-|-|
|既存のマーケティングでは顧客に有効にアプローチできない|新商品売上やプロモーションの反応率|EC サイトや既存店舗の売上データ、各種ログ|
|顧客のサービス継続率が低下してきている|顧客満足度やサービス継続率|ユーザマスタ、CRM マスタ、サービス利用ログ| 

仮説検証を繰り返す必要がある
 - 仮説を探すことが重要
 - 仮説検証の結果、次の仮説が生まれる

### 何から始めるべきか

- 課題とゴールを決める
- 小さく初めて収集から指標の評価までのフローを作ってみる

### オンプレミスで構築する場合の課題

 - 導入コスト
 - インフラ構築運用の作業が重く、データ分析に時間をさくのが難しい
 - 初期費用がかかり、失敗のリスクが大きい

<span style="font-weight: bold;">→ マネージドサービスやサーバーレスのサービスであれば、</span>
 - アプリケーション開発だけに集中できる 
 - データをどのように活用するかという本質に集中できる
 - データ活用の検討当初など、利用が少ない場合はコストがかからずに済む

### [Amazon QuickSight](https://aws.amazon.com/jp/quicksight/)

手軽に始められるBIのサーバレスサービス

 - 運用管理不要
 - 閲覧ユーザーの料金体系 → アクセスがなければ0円で済む
 - ブラウザのみで完結

### 事例 株式会社ファイブニーズ様

構成
 - Amazon RDS
 - Amazon QuickSight

課題
 - 売り上げデータをスプレッドシートで管理
 - データ転記の手間、人的ミス
 - 売り上げがわかるのが早くても翌日

### 事例 レッドフォックス株式会社様

構成
 - Amazon RDS
 - Amazon QuickSight
   - SPICE(インメモリ計算エンジン)

課題
 - ダッシュボードを使うユーザーの意見を即座に反映させる改善サイクルを作り、早く回す必要があった

1ヶ月強でシステム構築できた

### 事例 株式会社EXIDEA様

構成

S3を中心に置いたデータレイク構成にしている
 - データベース
   - Amazon RDS
 - ログ
   - Amazon Kinesis Data Firehose 
 - ETL
   - AWS Glue
   - Amazon S3
 - 可視化
   - Amazon QuickSight
   - Amazon Athena

課題
 - EmmaToolsTMで蓄積したデータを 有用に活用しきれていなかった
 - 提供している各機能の利用状況を把握して機能の改善や新機能開発に役立てたい

感想
 - 「データレイクを構築するにあたりAWSを活用した事例や技術などの情報量が多かった為、 サーバーレスサービスを活用し、1ヶ月程度で構築することができました。」