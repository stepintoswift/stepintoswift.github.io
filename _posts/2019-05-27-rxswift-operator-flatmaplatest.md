---
author: "Liam"
category: "RxSwift"
date: 2019-07-01 00:00:04
description: "FlatMapLatest Operator"
layout: post
permalink: rxswift-operator-flatmaplatest
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, FlatMapLatest, Transforming]
title: "What is the FlatMapLatest Operator in RxSwift?"
---

## RxSwift: FlatMapLatest Operator

`.flatMapLatest { }`

- Combination of [`.map`]({% post_url 2019-05-27-rxswift-operator-map %}) and [`.switchLatest`]({% post_url 2019-05-27-rxswift-operator-switchlatest %})
- FlatMaps as a normal [`.flatMap`]({% post_url 2019-05-27-rxswift-operator-flatmap %}) but when a new observable is emitted from a new Observable it
unsubscribes from the previous Observable.
- Useful for networking operations.
