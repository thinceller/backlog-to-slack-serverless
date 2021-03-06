# backlog-to-slack-serverless

元リポジトリ: https://github.com/dorachan/backlog2slack-serverless

元記事: Backlog通知をサーバレス構成でslackに飛ばす on @Qiita
http://qiita.com/kosuge/items/051922673cf57203f8db

## 下準備など

* BacklogやSlack側の設定は元記事をご確認ください
* 元記事にある環境変数は、 [serverless.yml](serverless.yml#L17) の中に記述します。
* [Serverless Framework](https://serverless.com/framework/) の環境設定を済ませておいてください。
* AWS環境はCLIのデフォルト設定を使います。あらかじめCLIを使えるようにしておいてください。

## デプロイ

```
npm install
sls deploy
```

## Lambda削除

```
sls remove
```

* Lambda関数のデプロイ(S3経由)、ロールの設定、API Gatewayの設定がまとめて完了します。AWSコンソールで操作する必要はありません。
* API URLはデプロイ後に表示されます。それを元記事に従い Backlog WebHook に設定してください。

## 削除

`sls remove`

* デプロイしたものが全て削除されます(ロール, API Gateway, S3など全て含む)
