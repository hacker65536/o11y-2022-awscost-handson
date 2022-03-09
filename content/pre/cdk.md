---
title: 'CDKなどの環境準備'
date: 2022-03-01T23:35:37+09:00
draft: false
---

## node の準備

cdk は nodejs が必要となります。

[nodenv](https://github.com/nodenv/nodenv),[nvm](https://github.com/nvm-sh/nvm),[asdf](https://asdf-vm.com/guide/getting-started.html#_5-install-a-version)などで node 環境を整えてください。

一番手順が少ない nvm を例としています。慣れていれば asdf などで管理するのが良いかもしれません。

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

terminal を立ち上げ直す or rc ファイルを読み込ます。利用している shell によって変えてください。

```
source ~/.bashrc
```

`v14.19.0`をインストールします。

```
nvm install v14.19.0
```

使用するバージョンを指定します。

```
nvm use 14
```

npm のアップデートを行います。

```
npm i -g npm@latest
```

## aws-cli の設定

awscli がない場合は brew で install します。

```
brew install awscli
```

profile と region の設定を確認します。

```
cat ~/.aws/config
```

```ini
[profile default]
region = us-east-1
cli_pager =
```

`default`以外の profile を利用している場合は環境変数を設定して切り替えします。

```
export AWS_PROFILE=myprofile
```

現在の aws の設定を確認します。

```
aws configure list
```

認証が問題ないかを確認します。

```
aws sts get-caller-identity
{
    "UserId": "AIXXXXXXXXXXXXX",
    "Account": "123456789012",
    "Arn": "arn:aws:iam::123456789012:user/myname"
}
```

## vscode

https://azure.microsoft.com/ja-jp/products/visual-studio-code/

IDE は vscode がとてもはかどります。

extensions の検索欄から`aws toolkit`を入力し、候補を選んで install します。

![vscode extension aws_toolkit](/images/ss_vs_ext_aws_toolkit.png)

cdk は preview で対応しています。
![vscode extension aws_toolkit](/images/ss_vs_ext_aws_toolkit2.png)

## install cdk

```
npm install -g aws-cdk
```

```
cdk --version
```

{{% notice info %}}
2022/03/08 時点の最新バージョン `2.15.0 (build 151055e)`
{{% /notice %}}

cdk で利用する asset などのアップロード先の s3 を作成する stack を作成します。

```
cdk bootstrap
```

{{% notice note %}}
各リージョンで cdk を初めて利用するときにだけ実行する
{{% /notice %}}



## プロジェクトのダウンロード


リポジトリをcloneします。
```
git clone https://github.com/hacker65536/awscost
```

```
cd awscost
```

モジュールのinstallをします。
```
npm i
```


`cdk.context.json`のslacktokenとslackchannelを自分のものに置き換えます。
```json
{
  "acknowledged-issue-numbers": [
    19179
  ],
  "CurReportName": "o11y2022-cur",
  "slacktoken": "xoxp-TOKEN",
  "slackchannel": "#channnel_name"
}
```