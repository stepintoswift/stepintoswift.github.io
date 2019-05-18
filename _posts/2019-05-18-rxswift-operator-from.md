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

## RxSwift: `from` operator

— Only takes an array of elements.
— Creates an observable of individual type instances from a regular array of elements.
— The produced type is an `Observable` of the supplied type NOT an array of the supplied type;.

```
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable = Observable.from([lotteryNumberOne, lotteryNumberTwo, lotteryNumberThree])
// Observable of Int
```