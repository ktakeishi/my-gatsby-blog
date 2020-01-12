---
templateKey: blog-post
title: gitでpush/pullするときに毎回パスフレーズを聞かれる時の話
date: 2020-01-12T03:14:41.824Z
description: >-
  githubでリモートリポジトリとの通信でhttpsではなくssh接続にしたはずなのに、git pushやgit pull、git
  cloneコマンドを叩いた時に、毎回パスフレーズの入力を求められるので、省略したい時に行った作業ログです。
featuredpost: true
featuredimage: /img/yancy-min-842ofhc6mai-unsplash.jpg
tags:
  - tips
  - git
---
このブログのソースコードはgithubのリポジトリで管理しており、ブランチをこのブログのソースコードはgithubのリポジトリで管理しており、ブランチを  

<サムネイル画像>  
<a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@yancymin?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Yancy Min"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Yancy Min</span></a>
