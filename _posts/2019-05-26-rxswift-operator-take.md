---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:09
description: "What is the Take Operator in RxSwift?"
layout: post
permalink: rxswift-operator-take
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Take]
title: "Take Operator"
---

## RxSwift: Take Operator

`Take(n)`

- Emits only the the first `n` elements and ignores everything after.

```
----7--9-----1--4---->

take(2)

----7--9------------->
```