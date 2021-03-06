---
author: "Liam"
category: "RxSwift"
date: 2019-07-01 00:00:06
description: "Scan Operator"
layout: post
permalink: rxswift-operator-scan
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Scan, Transforming, Accumulator]
title: "What is the Scan Operator in RxSwift?"
---

## RxSwift: Scan Operator

`.scan { }`

- Applies a supplied predicate to the elements emitted by an Observable, sequentially, emitting each successful result.
- Applies function to first element and then uses the result of this as the parameter for the second emitted elements applied function, and so on.
- Acts like an accumulator.
- Useful for for running totals, statistics, states...

```
--1--2--3--4--------5-------->

scan((x, y) => x * y)

--1--2--6--24-------120------>
```
