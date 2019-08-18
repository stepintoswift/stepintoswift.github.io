---
author: "Liam"
category: "RxSwift"
date: 2019-06-24 00:00:10
description: "TakeWhile Operator"
layout: post
permalink: rxswift-operator-takewhile
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, TakeWhile, Filtering]
title: "What is the TakeWhile Operator in RxSwift?"
---

## RxSwift: TakeWhile Operator

`TakeWhile { predicate }`

- Receives a predicate and takes everything up until the predicate is `false` and then does not let anything through.
- `true` = take
- `false` = don't take

```
----7--9-----1--4---->

takeWhile { x != 1}

----7--9------------->
```
