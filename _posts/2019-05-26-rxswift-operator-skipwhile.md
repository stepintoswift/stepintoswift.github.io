---
author: "Liam"
category: "RxSwift"
date: 2019-06-24 00:00:07
description: "SkipWhile Operator"
layout: post
permalink: rxswift-operator-skipwhile
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, SkipWhile, Filtering]
title: "What is the SkipWhile Operator in RxSwift?"
---

## RxSwift: SkipWhile Operator

`skipWhile { predicate }`

- Receives a predicate and skips everything up until the predicate is `false` and then let everything through.
- `true` = skip | `false` = don't skip | Works the opposite to `filter`!

```
----7--9-----1--4---->

skipWhile { x != 1 }

-------------1--4---->
```
