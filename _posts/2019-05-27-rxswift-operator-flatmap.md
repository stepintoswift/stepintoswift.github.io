---
author: "Liam"
category: "RxSwift"
date: 2019-07-01 00:00:03
description: "FlatMap Operator"
layout: post
permalink: rxswift-operator-flatmap
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, FlatMap, Transforming]
title: "What is the FlatMap Operator in RxSwift?"
---

## RxSwift: FlatMap Operator

`.flatMap { }`

- Projects and transforms the observable values of an Observable via a supplied predicate and then flattens them down to a single observable.
- Useful to filter out `nil`.
- Only emits values of an observable when then observable completes.

```
-----YY---------------YY---YY--->

flatMap { YY -> XX}

-----XX---------------XX---XX--->
```
