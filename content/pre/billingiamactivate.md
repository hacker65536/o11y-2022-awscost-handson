---
title: 'billing情報のIAMアクセス有効化'
date: 2022-03-01T23:33:21+09:00
draft: false
weight: 1
---

billing 情報を root ユーザ以外からもアクセスできるように変更する

root ユーザで AWS マネジメントコンソール にログインして、右上のメニューから `Account`をクリックして アカウント設定ページに移動する
![menu account](/images/ss_menu_account.png)

iam user/role から billing 情報にアクセスできるように `Activate IAM Access`にチェックして update ボタンを押下する

![activate iam access](/images/ss_account_settings_iam_access_to_billing.png)


{{% notice tip %}}
organizationsも設定して置くと良い
{{% /notice %}}