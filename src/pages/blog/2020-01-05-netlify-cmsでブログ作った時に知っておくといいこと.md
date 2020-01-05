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
このブログはNetlify CMSで作りました。  
まぁドメイン見りゃがっつり「netlify」と入っているので、説明するまでもないですね。  
  
Netlify CMSは、JAM Stackという爆速サイト作りたきゃこうやりな！的なことを提唱した人がやっているNetlifyという会社が提供しているブログサービスです。  

参考：[Netlify CMS](https://www.netlifycms.org/https://www.netlifycms.org/)  
  
  
JAM Stackを取り入れたサイトがどんなもんか手っ取り早く体感するために、手始めにこのサービスを使ってこのブログを作りました。レイアウトを少しいじった程度でほぼプレーンな状態です。  

前置き長くなりましたが、このブログを作る時に以下の２つのポイントでつまづきました
- サイトのタイトルとディスクリプションの変更
- 日本語の記事データからの抜粋文の取得方法

このブログはNetlify CMSで作りました。  
まぁドメイン見りゃがっつり「netlify」と入っているので、説明するまでもないですね。  
  
Netlify CMSは、JAM Stackという爆速サイト作りたきゃこうやりな！的なことを提唱した人がやっているNetlifyという会社が提供しているブログサービスです。  

参考：[Netlify CMS](https://www.netlifycms.org/https://www.netlifycms.org/)  
  
  
JAM Stackを取り入れたサイトがどんなもんか手っ取り早く体感するために、手始めにこのサービスを使ってこのブログを作りました。レイアウトを少しいじった程度でほぼプレーンな状態です。  

前置き長くなりましたが、このブログを作る時に以下の２つのポイントでつまづきました
- サイトのタイトルとディスクリプションの変更
- 日本語の記事データからの抜粋文の取得方法

## サイトのタイトルとディスクリプションの変更
これは調べたら瞬殺でした。  
わかりやすかったのは以下の記事↓  
[Gatsby.js + NetlifyCMSのデータの流れまとめ(+投稿画面、URLのカスタマイズ)](https://qiita.com/program_diary/items/f9056dc0d3e017359acdhttps://qiita.com/program_diary/items/f9056dc0d3e017359acd)  

要点だけまとめると、サイトのタイトルとディスクリプションの編集は、「gatsby-config.js」で行えます。

![実際のgatsby-config.jsのキャプチャ](/img/ss-gastby-config.png)
