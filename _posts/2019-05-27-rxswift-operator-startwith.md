---
author: "Liam"
category: "RxSwift"
date: 2019-07-08 00:00:07
description: "StartWith Operator"
layout: post
permalink: rxswift-operator-startwith
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, StartWith, Combining]
title: "What is the StartWith Operator in RxSwift?"
---

## RxSwift: StartWith Operator

`.startWith(_:)`

- Emits a supplied sequence of elements before beginning to emit elements from the source Observable.
- Must be the same type as the Observable elements.
- If you want to append to the end, use the [`.concat(_:)`]({% post_url 2019-05-27-rxswift-operator-concat %}) `concat` operator.

```
----------7-------6--------->

startWith(8)

-8--------7-------6--------->
```
