---
author: "Liam"
category: "RxSwift"
date: 2019-07-15 00:00:13
description: "WithLatestFrom Operator"
layout: post
permalink: rxswift-operator-withlatestfrom
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, WithLatestFrom, Combining]
title: "What is the WithLatestFrom Operator in RxSwift?"
---

## RxSwift: WithLatestFrom Operator

`.withLatestFrom()`

- Combines the emission of multiple Observables via a supplied function by combining each element from `self` with the latest element from the second source.
- When `self` emits an element, it will combine with the latest from the second Observable.
- If `self` emits and the second Observable does not have a value yet, nothing will emit.
- Useful for user interfaces. Say, `tap` plus the latest value in a `UITextField`.
- Similar to the `sample` operator only, with `withLatestFrom` takes data as a parameter.

```
---1---------2------3-------4----------5-------->
------a-b-------c-d-----e-f----g----h-------i--->

withLatestFrom

-------------2b-----3d-----4f---------5h-------->
```
