---
author: "Liam"
category: "RxSwift"
date: 2019-05-19 00:00:03
description: "What is the Empty Operator in RxSwift?"
layout: post
permalink: rxswift-operator-empty
published: true
tags: [Rx, ReactiveX, RxSwift, Empty, Operators, Operators]
title: "Empty Operator"
---

## RxSwift: Empty Operator

- Emits no elements followed by a `.completed` event.
- Useful when you want to return an observable that immediately terminates or intentionally has zero values.

```swift
let observable = Observable<Void>.empty()
```
