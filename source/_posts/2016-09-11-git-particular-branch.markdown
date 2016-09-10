---
layout: post
title: "git-特定のブランチを指定してclone"
date: 2016-09-11 08:02:12 +0000
comments: true
published: true
categories: [git]
---

リモートから特定のブランチを指定してcloneには以下を実行

{% codeblock lang:bash git-particular %}
$ git clone -b [blanch_name] https://[repository_address]
{% endcodeblock %}

