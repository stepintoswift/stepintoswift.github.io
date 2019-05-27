---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:17
description: "Reduce Operator"
layout: post
permalink: rxswift-operator-reduce
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Reduce, Combining, Accumulator, Aggregate]
title: "What is the Reduce Operator in RxSwift?"
---

## RxSwift: Reduce Operator

`.reduce (_:_:)`

- Sequentially applies a function to each element emitted by an Observable.
- Also known as an "accumulator" / "aggregate" operator.
- Take the element emitted from an Observable and passes this along as the result of the function until the Observable ends where it then emits the final resulting value.

```
----9-----2-----1-------3------|----->

reduce((x, y) => x-y)

-------------------------------3----->
```
