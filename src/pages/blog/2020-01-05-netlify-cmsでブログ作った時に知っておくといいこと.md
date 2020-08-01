---
templateKey: blog-post
title: Netlify CMSでブログ作った時に知っておくといいこと
date: 2020-01-05T09:30:50.102Z
description: >-
  Netlify
  CMSを使ってブログを立ち上げてカスタマイズしようとした時に、サイトタイトルとディスクリプションの編集と抜粋文の取得の仕方でちょっとつまづいたので、その時の対応内容を書き残します。
featuredpost: true
featuredimage: /img/sai-kiran-anagani-5ntkpxqt54y-unsplash.jpg
tags:
  - tips
  - Netlify CMS
  - gatsby
---
このブログはNetlify CMSで作りました。\
まぁドメイン見りゃがっつり「netlify」と入っているので、説明するまでもないですね。  

Netlify CMSは、JAM Stackという爆速サイト作りたきゃこうやりな！的なことを提唱した人がやっているNetlifyという会社が提供しているブログサービスです。  

参考：[Netlify CMS](https://www.netlifycms.org/https://www.netlifycms.org/)  

JAM Stackを取り入れたサイトがどんなもんか手っ取り早く体感するために、手始めにこのサービスを使ってこのブログを作りました。レイアウトを少しいじった程度でほぼプレーンな状態です。  

前置き長くなりましたが、このブログを作る時に以下の２つのポイントでつまづきました

* サイトのタイトルとディスクリプションの変更
* 日本語の記事データからの抜粋文の取得方法

このブログはNetlify CMSで作りました。\
まぁドメイン見りゃがっつり「netlify」と入っているので、説明するまでもないですね。  

Netlify CMSは、JAM Stackという爆速サイト作りたきゃこうやりな！的なことを提唱した人がやっているNetlifyという会社が提供しているブログサービスです。  

参考：[Netlify CMS](https://www.netlifycms.org/https://www.netlifycms.org/)  

JAM Stackを取り入れたサイトがどんなもんか手っ取り早く体感するために、手始めにこのサービスを使ってこのブログを作りました。レイアウトを少しいじった程度でほぼプレーンな状態です。  

前置き長くなりましたが、このブログを作る時に以下の２つのポイントでつまづきました

* サイトのタイトルとディスクリプションの変更
* 日本語の記事データからの抜粋文の取得方法

## サイトのタイトルとディスクリプションの変更

これは調べたら瞬殺でした。\
わかりやすかったのは以下の記事↓\
[Gatsby.js + NetlifyCMSのデータの流れまとめ(+投稿画面、URLのカスタマイズ)](https://qiita.com/program_diary/items/f9056dc0d3e017359acdhttps://qiita.com/program_diary/items/f9056dc0d3e017359acd)  

要点だけまとめると、サイトのタイトルとディスクリプションの編集は、「gatsby-config.js」で行えます。

![実際のgatsby-config.jsのキャプチャ](/img/ss-gatsby-config.png)

上の赤枠部分の文字列を変えるだけで、簡単にサイトのメタ情報を書き換えられます。  

## 日本語の記事データからの抜粋文の取得方法

これは小一時間悩みました。\
Netlify CMSの導入ステップに従ってサイトを構築すると、\
デフォルトのテーマ（コーヒーショップのKaldiのサイト）でサイトが立ち上がります。\
とりあえずは不要なコンテンツを消したり、レイアウト調整をしたりして\
サイトのベースだけ作り、最後に記事をデフォルトで入っていた記事を取り下げて\
自分が作成した記事を公開しました。  

**しかしここで問題が発生！**  

デフォルトの状態では表示されていた記事の抜粋文が表示されなくなってしまいました。\
抜粋文の文字数を変えるなどの変更はしましたが、それ以外の根本的な部分を変えた訳ではないのでどうしたものかと。。。  

こういう時はgoogle先生に聞きましょう！\
「gatsby excerpt 日本語」で検索し、以下のqiitaの投稿が出てきました。\
[Gatsbyのブログで日本語記事の抜粋（excerpt）を正しく表示させる方法](https://qiita.com/K-Kachi/items/03259fe07d1d3b89d6f3)  

> GatsbyでMarkdownを扱うgatsby-transformer-remarkは、デフォルトでunderscore.string/pruneを用いて抜粋をつくっているそうです。 しかし、これは非ラテン文字を扱えないため、日本語を用いる場合は変更する必要があります。

なるほどー日本語の抜粋文の取得の仕方については、少しだけ記述の仕方を変えなければいけなかったようですね。\
該当の箇所は以下の部分

/src/components/BlogRoll.js 74-80行\
【変更前】

```
edges {
  node {
    excerpt(pruneLength: 64)
    id
    fields {
      slug
    }edges {
```

具体的な変更方法は、上の`excerpt(pruneLength: 64)`を`excerpt(pruneLength: 64, truncate: true)`に変えるだけでした。  

【変更後】

```
edges {
  node {
    excerpt(pruneLength: 64, truncate: true)
    id
    fields {
      slug
    }
```

これで無事記事一覧の抜粋文が表示されました。\
まだまだブログ自体は適宜改修をしていくので、またこのようなつまづいたポイントが出てきたら記事にまとめたいと思います！  

今日はここまで
