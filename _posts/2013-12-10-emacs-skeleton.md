---
layout: post
title: "emacs skeleton"
description: ""
category: ""
tags: [emacs]
---
{% include JB/setup %}

emacs では、最大１個のユーザー入力を含むテンプレートは、skeleton で定義できる。

(skeleton-insert SKELETON) として記述すると、 Skeleton が表す文字列を挿入できる。
(INTERACTOR ELEMENTS) が skeleton の内容。
INTERACTOR は、先程述べたユーザー入力を受ける際のプロンプトとか。
ELEMENT は、文字列とか elisp とかサブ skeleton とか。
INTERACTOR は nil の値を与えることができ、その場合はユーザー入力はないものとして扱われる。
ユーザー入力は str 変数に束縛される。

ELEMENT が skeleton で、かつその skeleton がユーザー入力を受け取る場合、
ユーザーが空文字列を与えるまでそのサブ skeleton の挿入は繰り返し実行される。
これは elseif とかそういったものを表現するための機能。

ELEMENT が _ という変数の場合、 interesting point としての扱いをうける。
prefix argument でいろいろやると、そこに prefix argument で指定された文字列が入り込む。
詳細はもうちょっと調べてみないと分からない。

.emacs で使う場合は define-skeleton を使うと良さげ。

新しく作成するファイルのテンプレートも、 skeleton で記述ができる。
auto-insert を参照。
