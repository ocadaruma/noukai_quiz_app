# motto_quiz_motto

オプトの2016年上期納会で使用したクイズアプリから、オプト特有のものを抜き取って公開したものです。

## 概要

- スマホのブラウザ上で動くwebアプリ
- 管理コンソールで操作し、スマホに問題画面、回答画面を配信する（問題は４択）
- スマホで問題を回答する
- 回答の正誤や速度を元にランキングを発表する
- web socketで半リアルタイムに通信する

大人数でクイズをしたいときにぜひご利用ください。

## 機能

### スマホ画面の機能

- ログイン
  - 部署名、名前で認証する（ユニークであれば何でも可）
  - ログインユーザーの識別は簡略のためURLのみで行っています
- 問題待ち画面
  - ログイン・回答した後で問題が配られるまでの間の画面
- 回答画面
  - 配られた問題に対しての回答画面
  - 現在の回答数がリアルタイムに計上されます
  - リロードするともういちど選べるという仕様。。
- ボタン押すと音が出る機能
  - 画面下部に付けています
  - ちょっとした遊び心です


### 管理画面側の機能

web socketのサーバを操作して、端末側の画面を切り替えます

- 問題遷移画面
  - 端末へ問題の配信
  - 端末へ回答結果の配信
- ランキング画面
  - 得点数、回答速度でランキングを表示します
  - 下のおまけボタンを押した回数の集計画面

## 使い方

- フロントのコードを加筆してビルドする。
  - ログイン時の部署名もカスタマイズできます。
  - https://github.com/opt-tech/motto_quiz_motto/blob/for-oss/client/Readme.md#動かし方

- 問題文を入れ替える
  - https://github.com/opt-tech/motto_quiz_motto/blob/for-oss/client/questions.json

- サーバーを立ち上げる
  - https://github.com/opt-tech/motto_quiz_motto/blob/for-oss/server/README.md#使い方

- スマホからサーバーにアクセス
  - ログイン後、待機画面が出ます。
  - `http://<your server>/noukai_login`

- 管理PCから管理画面にアクセス
  - `http://<your server>/console`

- 問題を出す
  - 管理画面から操作できます。

- ランキングを表示する
  - 管理画面から「go ランキング」をクリックします。

## 技術

使っている主な技術を上げておきます。

- WebSocket
- React / Redux
- Typescript
- akka-http

## License

MIT
