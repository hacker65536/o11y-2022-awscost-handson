---
title: "Glue"
date: 2022-03-10T10:15:12+09:00
draft: false
weight: 100
---


## cloudforamtionの作成


![](/images/ss_glue_s3.png)

`cur`のデータ出力と一緒に`crawler-cfn.yml`というファイルがあります。

objectURLをクリップボードにコピーします。

cloudformationから`create stack`を選び、コピーしたobjectURLを Amazon S3 URLにペーストします。

![](/images/ss_cfn_create_stack.png)

stack nameは`awscost-athena-analyze`など適当な名前にして作成します。