---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:08
description: "What is the Of Operator?"
layout: post
permalink: rx-operator-of
published: true
tags: [Rx, ReactiveX, RxSwift, Of, Operator]
title: "Rx: Of Operator"
---

## Rx: Of Operator

- `.of` takes a variadic parameter.
- Creates an `observable` of the specified type (Not an array of that type unless you provide the parameter as an array).
- Type inference kicks in here so the type is not needed.

```
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable = Observable.of(lotteryNumberOne, lotteryNumberTwo, lotteryNumberThree)
// Observable of Int

let observable = Observable.of([lotteryNumberOne, lotteryNumberTwo, lotteryNumberThree])
// Observable ARRAY of Int
```
