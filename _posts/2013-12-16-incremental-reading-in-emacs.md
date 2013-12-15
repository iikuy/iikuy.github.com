---
layout: post
title: "Incremental Reading in Emacs"
description: ""
category: ""
tags: [emacs, Incremental Reading]
---
{% include JB/setup %}

Supermemo の Q&A は org-drill を使えば emacs 上で大体やりたいことはできるのだけれども。
Incremental Reading のようなことをお手軽に emacs 上でできないかとあれこれ悩んだ結果、
次のようにすれば良いのではないかという仮説に。

howm にて、読みたいファイルへのリンクを貼って、覚書として保存。
実際にそのファイルへ飛ぶ度に覚書の時刻を today に更新するようにする。
ファイルに飛んで、読みたいだけ読んだら、 bookmark 機能を使ってその場所を保存。
読み終わったファイルについては、覚書を削除して、もしまた繰り返し読みたいのであるならば、
そのリンクのみのノードを org-drill に無理矢理登録。
drill をやっててそれが出現したら、 quit して読みにいく or skip する。
