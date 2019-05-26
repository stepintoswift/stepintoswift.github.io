---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:12
description: "DistinctUntilChanged Operator"
layout: post
permalink: rxswift-operator-distinctuntilchanged
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, DistinctUntilChanged]
title: "What is the DistinctUntilChanged Operator in RxSwift?"
---

## RxSwift: DistinctUntilChanged Operator

`.distinctUntilChanged`

- Prevents duplicate contiguous elements from getting through.
- The 2nd element in the sequence will not get through.
- Elements that are `equatable` can be compared or you can provide your own comparison.

Comes in 2 forms:

- `.distinctUntilChanged()`
- `.distinctUntilChanged(_:)`

- `.distinctUntilChanged(_:)` is useful when you want to distinctly prevent duplicates for type that do not conform to equatable:

```
.distinctUntilChanged { a, b in a.value == b.value }
```

```
----1--2-----2--4----4--2-----2--4---->

distinctUntilChanged

----1--2--------4-------2--------4---->
```
