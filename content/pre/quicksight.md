---
title: 'Quicksightの有効化'
date: 2022-03-09T13:53:48+09:00
draft: false
---

aws マネージメントコンソールから検索欄などから `QuickSight`のホーム画面に移動します。

初めての場合は`sign up`が求められますので、sign up を行います。
![sign up for qs](/images/ss_qs_signup.png?classes=border)

edition は enterprise を選択します。
(最初の１ヶ月間 4 ユーザであれば無料)

![quicksight edition](/images/ss_qs_edition.png?classes=border)

次のページで、qs account nameを適当なユーザ名を入力します。またメールアドレスも登録します。
![quicksight create](/images/ss_qs_create.png?classes=border)

`Allow access and autodiscovery for these resources`でAmazon S3にチェックをし、curのs3 bucketをチェックします。

![quicksight create](/images/ss_qs_s3_acess.png)