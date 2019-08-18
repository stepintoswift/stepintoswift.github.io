---
author: "Liam"
category: "RxSwift"
date: 2019-06-10 00:00:04
description: "Never Operator"
layout: post
permalink: rxswift-operator-never
published: true
tags: [Rx, ReactiveX, RxSwift, Never, Operators, Operators]
title: "What is the Never Operator in RxSwift?"
---

## RxSwift: Never Operator

- Creates an observable that does not emit anything and never terminates.
- Represents infinite duration.
- When subscribed to, neither the `onNext` nor the `onCompleted` ever emit.

```swift
let observable = Observable<Any>.never()
```
