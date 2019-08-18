---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:06
description: "Just Operator"
layout: post
permalink: rxswift-operator-just
published: true
tags: [Rx, ReactiveX, RxSwift, Just, Operators, Operators]
title: "What is the Just Operator in RxSwift?"
---

## RxSwift: Just Operator

- `.just` operator creates an observable sequence containing `just` a single element and a `.completed` event.
- Type inference means we don’t need to define the type.

```swift
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable: Observable<Int> = Observable<Int>.just(lotteryNumberOne)
// Observable containing just lotteryNumberOne i.e. 1
```
