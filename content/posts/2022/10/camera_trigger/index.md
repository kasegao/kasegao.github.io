---
title: "スマホカメラの外部トリガを作成する"
date: 2022-10-17T10:35:29+09:00
draft: false
categories: ["tech"]
tags: ["electronics"]
---

最近、研究用にスマホカメラの外部トリガを自作したのでその時の備忘録です。

## 原理

スマートフォンのカメラは音量調整信号でシャッターを切れるようになっています。
今回はこれを利用して Android 向けのカメラの外部トリガを作成しました。

公式のアクセサリ仕様はこちらに掲載されています。  
[3.5 mm ヘッドセット: アクセサリ仕様](https://source.android.com/docs/core/interaction/accessories/headset/plug-headset-spec)

上記のドキュメントにある通り、マイク信号線とGNDを240(or 470)オームの抵抗を挟んで導通させれば、音量調整信号が送られるという事になります。

## 実装

今回は 3.5mm の 4 極プラグが手元になかったので下のピンチケイヤホンからパーツを拝借しました。

{{< amazon asin="B085NMRF99" title="3.5mmイヤホン マイク リモコン付き 有線 イヤホン HiFi 低音 ステレオイヤホン 通話可能 音量調整 騒音低減 ホワイト" >}}

オリジナルの状態です。

{{< figure src="images/origin.jpg" width="600" >}}

音量調整リモコンです。

{{< figure src="images/remocon.jpg" width="600" >}}

リモコンをバラシてはんだを外します。

{{< figure src="images/remove.jpg" width="600" >}}

導線を繋いではんだ付けします。汚いですが赦してください。短絡してなければ大丈夫です。  
※不安であればここで一度導通チェック等行ってください。

{{< figure src="images/extend.jpg" width="600" >}}

こんな感じで抵抗を挟んで直列に接続します。

{{< figure src="images/circuit.jpg" width="600" >}}

`18e` に半挿ししているジャンパーピンを抜き差しするとシャッターが切れます。

{{< video mp4="videos/comp.mp4" webm="videos/comp.webm" preload="auto" width="600" >}}

## 実装した感想

楽しい！！