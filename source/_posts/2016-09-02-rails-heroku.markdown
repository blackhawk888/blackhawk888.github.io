---
layout: post
title: "Railsで簡単なアプリを作ってHerokuにデプロイしてみる"
date: 2016-09-02 16:28:45 +0000
comments: true
published: false
categories: ['rails', 'heroku']
---

<!--more-->

Herokuのデプロイ方法だけを書こうと思ったが、適当なアプリを作ってHerokuにデプロイしたほうが備忘録としてよいかなと思ったので、残して置く。

要件はこんな感じ。

- Ruby on Rails(ver.4.2.6)
- Ruby(ver.2.3.0p0)
- CSS framework(Bootstrap)
- DB(development:sqlite、
- PaaS(Heroku)
- VCS(Git ver.2.8.4)

アプリといってもHerokuへのデプロイ方法がメインなのでメッセージを書いて表示できる程度の簡単なもの。    
scaffoldは使わない、簡単にアプリケーションの雛形を作成してくれるが、今回いちから作成することとする。    
ログイン等の実装はせず名前、年齢、メッセージを投稿でき、blankだったらエラーmsgと年齢に制限を設けるバリデーションを実装する程度。

### コントローラの作成

messageコントローラを作成

{% codeblock lang:ruby messages_controller.rb %}
$ rails generate controller messages index

      create  app/controllers/messages_controller.rb
       route  get 'messages/index'
      invoke  erb
      create    app/views/messages
      create    app/views/messages/index.html.erb
      invoke  test_unit
      create    test/controllers/messages_controller_test.rb
      invoke  helper
      create    app/helpers/messages_helper.rb
      invoke    test_unit
      invoke  assets
      invoke    coffee
      create      app/assets/javascripts/messages.coffee
      invoke    scss
      create      app/assets/stylesheets/messages.scss
{% endcodeblock %}


### routes.rbの設定

`config/routes`

{% codeblock lang:ruby routes.rb %}
Rails.application.routes.draw do
  get 'messages/index'
end
{% endcodeblock %}

### モデルの作成

{% codeblock lang:ruby message.rb %}
$ rails generate model Message name:string  age:string body:string
  invoke  active_record
  create    db/migrate/XXXXXXXXXXX_create_messages.rb
  create    app/models/message.rb
  invoke    test_unit
  create      test/models/message_test.rb
  create      test/fixtures/messages.yml
{% endcodeblock %}
