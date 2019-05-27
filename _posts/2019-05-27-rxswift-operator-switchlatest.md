---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:05
description: "SwitchLatest Operator"
layout: post
permalink: rxswift-operator-switchlatest
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, SwitchLatest, Combining]
title: "What is the SwitchLatest Operator in RxSwift?"
---

## RxSwift: SwitchLatest Operator

`.switchLatest { }`

- Emits values from the most recent Observable and the unsubscribes from the previous emitting Observable.
- Unsubscribes from previous Observable when a new Observable is emitted from the source Observable, not when
the new Observable emits an element. (i.e. The last `X` below will not be emitted.)

```
-------------------------------->
---X----X-X---X----------------->
|||||||||||||---Y------Y-----Y-->

`switchLatest`

---X----X-X-----Y------Y-----Y-->
```
