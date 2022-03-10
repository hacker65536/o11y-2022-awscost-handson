---
title: 'IAMユーザ作成'
date: 2022-03-07T12:33:48+09:00
draft: false
weight: 5
---

## user group 作成

`IAM` のホームページに移動します。

`User groups`を選び、`Create group`ボタンを押します。

`admin`を入力します。

Attach permissions policies から`AdministratorAccess`を選びチェックします。

`create group`します。

![](/images/ss_iam_create_group.png)


## iam user 作成

`Access key Programmatic access`
`password - AWS Management Console access`の２つをチェックをします。

![](/images/ss_iam_create_user.png?classes=border)

`admin`のgroupに入るようにチェックをします。

![](/images/ss_iam_create_user2.png)
そのままstep5まで進んで作成します。

keyidとcrednetialはメモしておきます。後ほどaws cliに設定します。