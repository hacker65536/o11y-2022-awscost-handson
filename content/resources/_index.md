---
title: 'リソース作成'
date: 2022-03-09T00:33:28+09:00
draft: false
weight: 20
---

[構成図]({{%relref "resources/structure.md"%}})

1. `cost & usage reports(cur)`の作成
   - s3
   - athena 用フォーマット出力のレポート
   - quicksight 用フォーマット出力のレポート
2. `glue`関連のリソース作成
   - datacatalog,database,table,crawler
   - cur の s3 に出力された`crawler-cfn.yaml`を cloudformation で stack 作成
3. `athena`関連のリソース作成
   - workgroup、prestm、などの作成
4. `quicksight`関連のリソース作成
   - datasets
     - cur の s3 に出力されてた quicksight 用 `xxxxxxQuickSightManifest.json`を dataset として利用する
5.  slackにコストの分析結果を通知する`lambda`を作成

## cost & usage reports

cost & usage report(cur)は作成してからレポートが届くのに 24 時間から数日かかることがあるため事前に作成頂く必要があります。

aws マネージメントコンソールから作成できます。



cdk で`CurStack`を用意して、cdk からの作成も可能です。

## glue 関連のリソース作成

curを設定した場合、`crawler-cfn.yaml`というcloudformation用templateがs3のbucketに出力されます。
このyamlをcloudformationのstack作成用templateとして指定すると、athenaから連携できるように、s3との連携をいい感じにしてくれます。

datacatalogのdatabase/tableとcrawlerと、s3にレポートが届いたらlambdaで処理してくれる一連のリソースを作成してくれます。

## athena　関連のリソース作成

cdk の `AthenaStack`をdeployします。

コスト分析用のworkgroupを作成し、