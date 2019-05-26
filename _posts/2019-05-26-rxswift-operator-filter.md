---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:05
description: "Filter Operator"
layout: post
permalink: rxswift-operator-filter
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Filter]
title: "What is the Filter Operator in RxSwift?"
---

## RxSwift: Filter Operator

`filter()`

- Only allows though elements that pass a defined predicate test.
- Applies to the life of the subscription.

```
----1--20-----33--49---->

filter(x => x > 30)

--------------33--49---->
```
