---
layout: post
title: "MercurialとGitコマンド比較"
date: 2016-09-01 15:16:42 +0000
author: wivern
comments: true
published: true
categories: ['git', 'mercurial']
---

gitはいつも使っているのだが、他のVCSとしてSubversion、Bazaar、Mercurialとあるが、
最近Mercurialが気になっていてコマンドの違いを比較してみた。

gitとMercurial の特徴は以下のとおり

<!--more-->

### Mercurial の特徴
 - クロスプラットフォームの分散型バージョン管理システム
 - ライセンスはGPL v2
 - 高度なブランチ機能とマージ機能がある。
 - Webインターフェイスもある。
 - 他のバージョン管理システムで管理されたソースコードを取り込む機能がある。

### Git の特徴
 - 分散型バージョン管理システム 
 - ライセンスはGPL v2 
 - 中央サーバへのアクセスが不可能な状態であってもリビジョン間の履歴を調査することができる。

| Mercurial | Git |
|:--|:--|
| hg add | git add |
| hg blame | git blame |
| hg cat | git show |
| hg clone |git clone |
| hg commit ; hg push | git commit -a ; git push |
| hg remove | git rm 
| hg diff | git diff, git diff –cached |
| hg help | git help |
| hg log | git log |
| hg revert | git checkout -f |
| hg status | git status |
| hg pull –update | git pull |
| hg move/rename | git mv |

Subversion のものにとても似ているようなので、その2つのツール間の移行を容易にしていると思われる。


