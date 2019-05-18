---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: variable
published: false
tags: [variable var]
title: "Variable"
---

## RxSwift: `just` operator

— `.just` operator creates an observable sequence containing `just` a single element and a `.completed` event.
— Type inference means we don’t need to define the type

```
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable: Observable<Int> = Observable<Int>.just(lotteryNumberOne)
// Observable containg just lotteryNumberOne i.e. 1
```
