---
title: AWS Innovate – Data Edition 見てきました。【その5】

# subtitle: Welcome 👋 We know that first impressions are important, so we've populated your new site with some initial content to help you get familiar with everything in no time.

# Summary for listings and search engines
summary: アクサダイレクトのデータ活用を強力に推進する仕組みとは

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

AWS Innovate – Data Editionのセッションを聴講した時のメモ その5


リンク元：[AWS Innovate – Data Edition 見てきました。](/post/aws_innovate_data_edition)

## アクサダイレクトのデータ活用を強力に推進する仕組みとは

|セッション|時間|スピーカー|
|-|-|-|
|CUS2-6<br/>お客様事例|15:20 - 15:50|アクサ損害保険株式会社<br>データ&テクノロジー本部 エンタープライズデータ部<br>岡崎 卓弥 様|

### アクサダイレクトについて 

 - 保険及び資産運用サービス
 - 世界で1億以上のユーザー
 - 「デジタル化」を中核とする企業戦略

### DX基盤作りの課題と背景

 - キャタピラ(コールセンターの電話システムの構築)
 - バタフライ(契約管理、保険料収納等の基幹システムの構)
 - ドラゴンフライ(事故対応・保険金請求等の システムの構築)

全てのプロジェクトのデータはデータレイクに溜めてきた。

表向きはデータ活用の基盤づくりが進んでいるように見えるが...

<!-- データレイクの内
 - データスワンプ状態
 - データエンジニア、データサイエンティストのみがデータを扱える状態
 - 欲しいデータがどこにあるかわからない
 - レポートなど成果物は全てデータ部門で作成して管理する

データレイクの外
 - BIツールやExcelの乱立
 - 維持管理に人的リソースがかかる
 - 社内ナレッジがたまらない -->

|データレイクの内|データレイクの外|
|-|-|
|<ul><li>データスワンプ状態</li><li>データエンジニア、データサイエンティストのみがデータを扱える状態</li><li>欲しいデータがどこにあるかわからない</li><li>レポートなど成果物は全てデータ部門で作成して管理する</li></ul>|<ul><li>BIツールやExcelの乱立</li><li>維持管理に人的リソースがかかる</li><li>社内ナレッジがたまらない</li></ul>|

### データレイクの再構築

 - 全てのエンドユーザーに最適な環境を提供する
   - Casual user
   - Business analyst
   - data scientist
 - BIツールは１つに局所化 → Amazon QuickSight
 - Redshiftがビジネスレイヤーを担当

Amazon QuickSighttを選んだ理由(他に3つ候補があった)
 - ユーザー当たり単価が安い
 - 追加でストレージ等を用意しなくて良い
 - データレイクはすでにAWS上に構築している → AWS内で完結するためセキュア

### ユーザーを支援する仕組み

基盤を整理するだけでなく、使われるように浸透させる必要がある

<span style="font-weight: bold;">組織体制</span>

データマネジメントオフィス
 - データ活用におけるルール・環境・文化醸成をリード
   - データポリシーやガイドラインの制定
   - データ品質/メタデータ/アクセス権の管理
   - データスチュワードのコミュニティを作り活動を支援
   - データ活用促進のためビジネスユーザに必要なトレ ーニング・支援を行う

データスチュアード
 - 各部門から任命、所管するデータに関する高度な知識を有する専門家
   - 各部門のデータ活用をリード
   - 所管するデータのデータ品質/メタデータ/アクセス権の管理
   - コミュニティへの参加

Amazon QuickSightサポート体制
 - 相談窓口やデータスチュアードへの質問、AWSサポートなどでレベル分けする

<span style="font-weight: bold;">ユーザーがデータに興味をもち、なるべく自走してデータ活用できる土壌を作る</span>

### 今後の展開

 - データの拡充
 - データスチュアード業務の高度化
 - ユーザーのスキルアップ
