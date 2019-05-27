---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:00
description: "ToArray Operator"
layout: post
permalink: rxswift-operator-toarray
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, ToArray, Transforming]
title: "What is the ToArray Operator in RxSwift?"
---

## RxSwift: ToArray Operator

`.toArray`

- Converts an observable sequence into an array of those elements and emits a `.next` event containing that array to subscribers.

```
----7--9-----1--4---->

toArray()

[----7--9-----1--4----]>
```
