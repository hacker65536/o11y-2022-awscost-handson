---
title: 'リソース削除'
date: 2022-03-10T09:27:30+09:00
draft: false
---

## cdk destroy

cdk で作成したスタックをすべて削除する

```
cdk destroy --all
```

## QuickSight サブスクリプション解除

右のメニューから`Manage QuickSight`を選び、管理画面に移動します。
![manage quicksight](/images/ss_qs_manage.png)

左のメニューから`Account settings`を選び `Delete account`をクリックします。

![](/images/ss_qs_account_settings.png)



## cost and usage report の削除


billingのホームからcost & usage reportsのメニューを選び、表示されているレポート選択してdeleteボタンを押します。
![](/images/ss_cur_delete.png)


curの出力先のs3 bucketを空にして、削除します。


## glueのリソースの削除


`crawler-cfn.yml`をcloudformationで作成しているので、このstackを削除します。


## 今回作成したIAM ユーザ、グループを削除


IAM のホームページから、groupsとusersを削除します。