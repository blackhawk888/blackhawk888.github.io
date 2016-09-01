---
layout: post
title: "Octopress-markdownでtableを作成できるようにする"
date: 2016-09-01 17:22:02 +0000
author: wivern
comments: true
published: true
categories: ['octopress']
---

前回記事でMercurialとGitのコマンド比較をするためMarkdownでTableを作成したのだが、
`bundle exec rake preview`を実行しても表が作成されない！
調べてたらTableをMarkdownで編集できるようにする方法があったので、
忘れないように書いておく

<!--more-->

### CSSファイルtable.cssの追加

`source/stylesheets/`に`table.css`を追加

{% codeblock lang:css table.css %}
* + table {
    border-style:solid;
    border-width:1px;
    border-color:#e7e3e7;
    margin: 10px 0 30px 0;
}

* + table th, * + table td {
    border-style:dashed;
    border-width:1px;
    border-color:#8888AA;
}

* + table th {
    border-top:    1px #666688 solid;
    border-bottom: 2px #666688 solid;
    font-weight:bold;
    background-color: #C0C0C0;
    padding: 2px 9px;
}

* + table td {
    border-bottom: 1px #666688 solid;
    background-color: #F0F0F0;
    padding: 0 10px;
}

* + table th[align="left"], * + table td[align="left"] {
    text-align:left;
}

* + table th[align="right"], * + table td[align="right"] {
    text-align:right;
}

* + table th[align="center"], * + table td[align="center"] {
    text-align:center;
}
{% endcodeblock %}

### headerにcssのリンクを追加

`source/_includes/head.html`にコードを追加

{% codeblock lang:html head.html %}
<link href="/stylesheets/table.css" rel="stylesheet" type="text/css" />
{% endcodeblock %}

### 記事のMarkdownファイルにTableを書く

{% codeblock lang:css exsample.md %}
hoge|foo|bar
:---|:--:|---:
aa|bb|cc|
{% endcodeblock %}

以下のように自動でテーブルに変換される

hoge|foo|bar
:---|:--:|---:
aa|bb|cc|
