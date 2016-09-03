---
layout: post
title: "Octopress-画像保存先"
date: 2016-09-03 22:30:43 +0000
comments: true
published: true
categories: [octopress]
---

Octopressでこのブログを投稿するときに画像を挿入する場合はGyazoを使っていたが、
Octopressのディレクトリ指定の仕方は[公式ブログ](http://octopress.org/docs/plugins/image-tag/)に書いてるとおり以下の設定をすればOK

{% codeblock lang:ruby Syntax %}
{% raw %}
{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
{% endraw %}
{% endcodeblock %}


### Examples

{% codeblock lang:ruby Syntax %}
{% raw %}
{% img http://placekitten.com/890/280 %}
{% img left http://placekitten.com/320/250 Place Kitten #2 %}
{% img right http://placekitten.com/300/500 150 250 Place Kitten #3 %}
{% img right http://placekitten.com/300/500 150 250 'Place Kitten #4' 'An image of a very cute kitten' %}
{% endraw %}
{% endcodeblock %}

<!--more-->

Octopressと同じサイト内で画像を挿入させるには、通常`source/images/`に画像を入れ、

{% codeblock lang:ruby Syntax %}
{% raw %}
{% img /images/exsample.png %}
{% endraw %}
{% endcodeblock %}

{% img  /images/exsample.png 300 400 %} 
{% img  right /images/exsample02.png 300 400 %} 


### Markdown形式の場合は

{% codeblock lang:ruby Markdown %}
![alt title](image URL)
{% endcodeblock %}

絶対指定をすると

{% codeblock lang:ruby Markdown %}
![exsample](https://blackhawk888.github.io/images/exsample.png)
{% endcodeblock %}

![exsample](https://blackhawk888.github.io/images/exsample.png)


相対指定をすると

{% codeblock lang:ruby Markdown %}
![exsample](/images/exsample02.png)
{% endcodeblock %}

![exsample](/images/exsample02.png)



