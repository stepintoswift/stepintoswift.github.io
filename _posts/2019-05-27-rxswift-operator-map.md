---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:01
description: "Map Operator"
layout: post
permalink: rxswift-operator-map
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Map, Transforming]
title: "What is the Map Operator in RxSwift?"
---

## RxSwift: Map Operator

`.map()`

- Applies a supplied function to each emitted element.
- Returns an Observable that emits the result after the function has been applied.
- Transforms the elements emitted by an Observable by applying a function to each element.
- Works like Swifts standard map except it operates on observables.

```
----1--2-----3--4---->

map(x -> x * 2)

----2--4-----6--8---->
```

```
.map { response in return response.url }
.map({ (response: urls) -> [Url] in return response.urls })

// or even better...

.map { $0.url }
.map { $0.urls }
``
