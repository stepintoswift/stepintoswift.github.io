---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:06
description: "Skip Operator"
layout: post
permalink: rxswift-operator-skip
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Skip, Filtering]
title: "What is the Skip Operator in RxSwift?"
---

## RxSwift: Skip Operator

`skip(n)`

- Skip a certain defined number of elements.
- Use case would be for events that have happened in the past that you do not care about.
- Ignores from the first element until the supplied elements

```
----1--2-----3--4---->

skip(2)

-------------3--4---->
```
