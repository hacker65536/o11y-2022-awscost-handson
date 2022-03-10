---
title: 'Quicksight'
date: 2022-03-10T10:27:24+09:00
draft: false
---

## datasets の作成

cur ので quicksight 形式のレポートを設定した場合 cur の s3 に`manifest.json`が出力されます。
このオブジェクトの S3URI をコピーします。

![](/images/ss_qs_create_dataset_from_s3.png)

QuickSight へ移動します。左のメニューから`データセット`を選び、右上の`新しいデータセット`を押します。

![](/images/ss_qs_create_dataset_new.png)

データソースに s3 を選択します。データソース名に`awscostanalysis`などの適当な名前を入力します。
マニフェストファイルは s3 のオブジェクトの S3URI をペーストします。
![](/images/ss_qs_create_dataset.png)

データセット作成完了しましたら、`視覚化する`を押します。
![](/images/ss_qs_dataset_success.png)
