---
title: 'CURの作成'
date: 2022-03-10T07:53:37+09:00
draft: false
weight: 10
---

aws マネージメントコンソールの検索欄から`billing`と入力し、`billing`のホーム画面に移動します。

![](/images/ss_billing_cur.png?classes=border)

左のメニューの`Cost & Usage Reports`を選択して cur の画面に移動します。
`create report`ボタンをクリックして作成します。

![](/images/ss_cur_create1.png)

{{% notice info %}}
Include resource IDs をチェックするとどのリソースがどれくらい利用しているのかの詳細データが見れるようになります。その代わり s3 に保存されるデータ量も増えます。
{{% /notice %}}

料金データの保存先の s3bucket を cur の作成画面から作成できます。
aws から料金データの object が put されるために、`billingreports.amazonaws.com`からの`putobject`許可が必要です。
`バケットポリシー`の一緒に作成してくれます。

![](/images/ss_cur_create_s3.png?classes=border)
![](/images/ss_cur_create_s3policy.png?classes=border)

report path prefix は athena 形式の場合は`athena`と入力し、quicksight の場合は`quicksight`と付けるとわかりやすいかもしれません。

時間粒度は、一番細かい`hourly`にすると詳細な情報が見られるようになります。

`enalbe report data integration for` は `Amazon Athena`を選びます。
`quicksight`のレポートの場合は`Aamazon QuickSight`を選びます。
![](/images/ss_cur_create2.png)

確認画面のあと問題なければ作成します。
