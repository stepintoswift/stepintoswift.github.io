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

## RXSwift: `of` operator

— `.of` takes a variadic parameter
— Creates an `observable` of the specified type (Not an array of that type unless you provide the parameter as an array)
— Type inference kicks in here so the type is not needed.


```
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable = Observable.of(lotteryNumberOne, lotteryNumberTwo, lotteryNumberThree)
// Observable of INT

let observable = Observable.of([lotteryNumberOne, lotteryNumberTwo, lotteryNumberThree])
// Observable array of Int
```