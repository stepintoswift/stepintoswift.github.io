---
author: "Liam"
category: "RxSwift"
date: 2019-06-17 00:00:03
description: "IgnoreElements Operator"
layout: post
permalink: rxswift-operator-ignoreelements
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, IgnoreElements, Filtering]
title: "What is the IgnoreElements Operator in RxSwift?"
---

## RxSwift: IgnoreElements Operator

`ignoreElements()`

- Ignores `onNext` events.
- Only lets through `onCompleted` / `onError` events (i.e. Stop events).
- Useful when you only want to be notified when sequence is terminated.

```
----1--2-----3--4---->

ignoreElements()

--------------------->
```
