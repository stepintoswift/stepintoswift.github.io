---
author: "Liam"
category: "RxSwift"
date: 2019-07-29 00:00:16
description: "Amb Operator"
layout: post
permalink: rxswift-operator-amb
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Amb, Switch]
title: "What is the Amb Operator in RxSwift?"
---

## RxSwift: Amb Operator

`.amb()`

- Stands for ambiguous operator.
- Given two or more Observables, only emit elements from the first Observable to emit an element / event.
- Waits for an Observable to emit and unsubscribes from the others.
- Only replays elements from the first active observable.

```
----1-----------3-----------5---->
------6---7----8----9------------>
--------2-----4------------------>

amb

----1------------3----------5---->
```
