+++
title = "About Me"
date = "2019-09-12"
+++

## はじめに
Kyo0228です。ご訪問ありがとうございます。このサイトはGithubPagesで公開した静的サイトです。テスト用途で構築しました。運用方法の確認も兼ねています。

## 当サイトのコンテンツ
思いっきりプライベートに寄せた私個人の思考ついて整理した記事となります。
この手法はNLPという心理学セミナーで紹介されたものです。

### 価値観の棚卸
人の価値観は変わるもの。１年ごとに「人生において何が大切か」に対する答えを整理します。自分自身とコミュニケーションをとり将来の方向性について明確にします。

### 今後の目標
今後やりたいこと、なりたいことについて整理します。これはNLPに限らず友人から勧められたり自己啓発本にもよく書かれていることですが目標達成までの期間や達成度についてもまとめていきます。


## 当サイトの構築、設定
自前サーバーでホスティングせず簡単に静的サイトを公開できる外部サービスを探していたところ、以下の参考サイトを拝見しました。

* 参考サイト
    * [Hugo + Travis CI + Github pagesで独自ドメイン+HTTPSなWebページを公開する](https://poyo.hatenablog.jp/entry/2018/06/08/145255)
    * ありがとうございました！
* 検索キーワード
    * Github Pages
    * 独自ドメイン
    * https
    * 無料
* 利用ツール、環境
    * Github
        * public公開
    * HUGO
        * Go言語で作られた静的サイトジェネレータ
    * Travis CI
        * Githubと連携可能なCIツール。HUGOのビルドを担当
        * publicだと無料で利用可
    * MacOS Mojave 10.14.5
    * Visual Studio Code

HUGO、Travis CIとも初めての利用でしたが参考サイトの通り設定を行うことで難なく開発、ビルド、公開環境が構築できました。
構築方法に関しては割愛します。


### HUGOのデザインテンプレート
HUGOには豊富なデザインテンプレートがあります。好みのテンプレートを探して始めてみましょう。

* テーマ（公式サイト）
    * [Hugo Themes](https://themes.gohugo.io/)

私は「Hermit」というテーマを選択。

* Hermit
    * [Hermit (Hugo Themes)](https://themes.gohugo.io/hermit/)
    * [Hermit (デモサイト)](https://themes.gohugo.io/theme/hermit/)


### Hermitの設定
デザインテンプレートのインストール、ローカル環境でのプレビューに関しても参考サイトの記載通りに進めます。
プレビュー実行後 `/posts` の表示で気になった日付表示について調べたところconfigファイルの変更で済むことがわかった

    config.toml 元
    [params]
      dateform        = "Jan 2, 2006"
      dateformShort   = "Jan 2"

↓

    config.toml 変更後
    [params]
      dateform        = "2006-01-02"
      dateformShort   = "01-02"

Go言語の日付フォーマットは「2006-01-02 15:04:05」で記載する。「yyyy-mm-dd」のようなフォーマット文字列ではないので注意。


### オリジナルCSSの設定
コンテンツのH2要素にボーダーラインを引くためオリジナルのCSSを追加しました。

staticフォルダにcssフォルダがなければ作成。cssファイルを作成する。
    
    css/style.css
    @charset "UTF-8";

    .content h2{
        border-bottom: solid 2px white; 
    }

configファイルに追加したcssファイルを設定。

    config.toml
      # Add custom css
      customCSS = ["css/style.css"]



## HUGOの感想
HUGOによる静的webサイト構築は本当に早く作れた！
参考にさせていただいたサイトのお陰でもありますがデプロイまで一気に解決。
用途に許容できるデザインテンプレートがあればローコスト、短期間での公開が可能です。

まだほとんどデザインテンプレートのデフォルト構成ですが、運用している上で有用な情報について今後も追記をしていきます。

