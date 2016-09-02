---
layout: post
title: "slack-googleカレンダー連携"
date: 2016-09-02 16:13:12 +0000
comments: true
published: true
categories: [slack]
---

Slackの外部サービス連携機能を使いgoogleカレンダーを連携させ
自分のスケジュールをSlack上で通知されるように設定する。

<!--more-->

### 連携手順

1. Slackログイン後、左メニュー上部に`Team`名が表示されているのでそれをクリック。  
2. `Apps & Custom Integrations`を選択
3. `App Directory`検索画面で`google calendar`を入力
4. 連携させたいSlackグループを選ぶ
5. Googleアカウントを同期させ、通知先のチャンネルを設定(どのチャンネルにも設定でき、自分だけに通知が飛ぶようにもできる)
6. 予定の何分前に通知するか、終日で設定されている予定はいつ通知するか、1日の予定のサマリーを通知するか、1周間の予定のサマリーを通知するか等の設定項目があるが好みで設定。
7. `save Integration`をクリックし保存
8. `Your calendar is connected!`と表示されるので`Im done!`をクリックし完了

上記の設定を行うと毎朝指定の時間に自分の1日の予定がSlack上に表示することが可能。



