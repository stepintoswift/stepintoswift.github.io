---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:12
description: "Zip Operator"
layout: post
permalink: rxswift-operator-zip
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Zip, Combining]
title: "What is the Zip Operator in RxSwift?"
---

## RxSwift: Zip Operator

`.zip()`

- Combines the emission of multiple Observables via a supplied function.
- Emits a single element for each combination based on the results of the supplied function.
- Function applied in strict order such that the first element emitted by the first Observable will be used with the first element emitted from the second Observable.
- It will only emit as many times as the fewest emitting Observable.
- Uses indexed sequencing.
- If one Observable completes, the output Observable completes.
- It does not wait until all the inner Observables are done.
- Multiple variants just like `combineLatest` - one variant for collections.

```
---1---------2------3-------4----------5-------->
------a-b-------c-------d------e----f-------g--->

zip

------1a-----2b------3c-----4d---------5e------->
```
