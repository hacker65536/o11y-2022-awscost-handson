---
title: 'Slackapp'
date: 2022-03-09T01:17:54+09:00
draft: false
---

## slack app の作成

{{% notice info %}}
slack app 作成には権限が必要です。  
full member 以上の権限が必要  
アプリの認証が有効化されていると admin 以上の権限が必要
{{% /notice %}}

slack のアプリのメニューから workspace の設定に移動します。
![slack workspace settings](/images/ss_slack_workspacesettings.png)

`Configure apps`をクリックして`app directory`に移動し、右上の`build`をクリックしてさらに`slack api`に移動します。

ブラウザ側でログイン済みであれば [https://api.slack.com/apps/](https://api.slack.com/apps/)に直接移動します。

`Create New App`
![create new slack app](/images/ss_slack_create_new_app.png)

manifest から作成を選びます。
![from manifest](/images/ss_slack_create_app_from_manifest.png?classes=border)

所属してる workspace を選び、manifest を以下の様に編集して next に進みます。
![from manifest](/images/ss_slack_app_manifest.png?classes=border)

```
display_information:
  name: awscost
features:
  bot_user:
    display_name: awscost
oauth_config:
  scopes:
    bot:
      - chat:write
settings:
  org_deploy_enabled: false
  socket_mode_enabled: false
  token_rotation_enabled: false
```

確認画面から create を押して作成します。

## slack app のインストール
slack appの設定画面から install your appの`install to Workspace`のボタンを押して、表示されたモーダルから`Allow`をクリックします。

右のメニューから`OAuth & Permissions`を選び、表示されている`Bot User OAuth Token`をメモしておきます。
