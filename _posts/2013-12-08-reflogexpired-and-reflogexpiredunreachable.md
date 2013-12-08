---
layout: post
title: "reflogexpired and reflogexpiredunreachable"
description: ""
category: ""
tags: [git]
---
{% include JB/setup %}


git の gc.reflogexpired と gc.reflogexpiredunreachable の違いが何なのか気になった。

http://git-scm.com/docs/git-gc によると、どうやら unreachable というのは、
その reflog を取っている対象の ref が、今現在指し示しているコミットオブジェクトから辿って到達できる
コミットオブジェクトを reachable, そうでないものを unreachable としている様子。

git reset --hard HEAD^ で、 reflog のみに今存在している最新版だったコミットは、
unreachable なコミットオブジェクトになるのでしょう。
