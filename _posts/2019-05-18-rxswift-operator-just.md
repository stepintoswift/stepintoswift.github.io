---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:06
description: "What is the just operator?"
layout: post
permalink: rx-operator-just
published: true
tags: [Rx, ReactiveX, RxSwift, Just, Operator]
title: "Rx: Just Operator"
---

## Rx: Just Operator

- `.just` operator creates an observable sequence containing `just` a single element and a `.completed` event.
- Type inference means we don’t need to define the type.

```
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable: Observable<Int> = Observable<Int>.just(lotteryNumberOne)
// Observable containing just lotteryNumberOne i.e. 1
```
