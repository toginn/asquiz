# アンケート型SNS Asquiz

![asquiz-cover](https://user-images.githubusercontent.com/89682463/172571147-512439cb-f122-4a5d-89ab-22768b940c11.png)

「気軽に質問できるSNS」をモットーにしたSNSです。

従来の質問投稿型サイトと違い、SNSの側面を重視していて、ユーザー同士で気軽に交流できるようなサービスを目指しました。

サービスURL: https://asquiz.jp

開発期間: 1ヶ月半

## ローカル環境実行

Docker Composeを用います。

```bash
$ git clone https://github.com/toginn/asquiz
$ cd asquiz
$ docker compose up -d
```

コンテナ起動後、`http://localhost:3000`からアクセス出来ます。

※ユーザー作成機能はSMTPユーザーが必要になりますので、`docker-compose.yaml`の17~21行目に、利用するSMTPユーザーの環境変数を設定してください。(ゲストログイン機能の場合は必要ありません)

## 主なユーザー利用機能

* ユーザー作成・ログイン
* ゲストユーザーログイン
* 質問の投稿
* 質問への投票
* 投票結果の表示
* マイページ
* 質問ランキング
* 質問検索
* 退会処理


## 技術スタック

![image](https://user-images.githubusercontent.com/89682463/172570808-d467f1a8-0d23-40d6-b5db-0a8ff2b6235d.png)

## アピールポイント

現代のWebアプリ開発に通用するモダンな技術を使用しました。
使用技術だけでなく、設計や保守性という観点から、**ドメイン駆動設計**と**型駆動開発**を中心に開発しました。
バックエンドのRestful APIはオブジェクト指向設計を用いています。

## Frontend

**TypeScript + Create-React-Apps**

Reactを用いたSPAを、Netlifyでホスティングしています。
Material UIによるレスポンシブデザインを意識しました。

## Backend

**TypeScript + Node.js + Fastify**

Node.jsベースのRestful APIをHerokuにデプロイしています。

## Infastructure

**Netlify + Heroku + MongoDB Atlas + onamae.com + SendGrid + Jest**

基本的に無料で使えるサービスから構成されています。サーバーに関しては、CI/CDパイプラインの設定により、mainブランチが自動でデプロイされるようになっています。
