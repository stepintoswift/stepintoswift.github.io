---
author: "Liam"
category: "RxSwift"
date: 2019-07-15 00:00:11
description: "CombineLatest Operator"
layout: post
permalink: rxswift-operator-combinelatest
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, CombineLatest, Combining]
title: "What is the CombineLatest Operator in RxSwift?"
---

## RxSwift: CombineLatest Operator

`.combineLatest()`

- Combine the latest values from each supplied Observable using a supplied function.
- Both Observables need to emit an element for combining to happen.
- Operator receives a closure predicate that is applied to each emitted element.
- The latest elements from each Observable are combined.
- You can combine sequences of heterogenous types - Only core operator that allows this.
- Can use [`startWith(n)`](% post_url 2019-05-27-rxswift-operator-startWith %) to kick things off.
- Only completes when the last of its inner sequences completes.
- Multiple variants taking between 2 and 8 Observable sequences as parameters - One that takes an array.

```
---1---------2------3-------4----------5-------->
------a-b-------c-------d------e----f-------g--->

combineLatest((x, y) => "" + x + y)

------1a-1b--2b-2c--3c--3d--4d-4e---4f-5f---5g-->
```
