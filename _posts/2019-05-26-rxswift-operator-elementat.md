---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:04
description: "ElementAt Operator"
layout: post
permalink: rxswift-operator-elementat
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, ElementAt]
title: "What is the ElementAt Operator in RxSwift?"
---

## RxSwift: ElementAt Operator

`elementAt(n)`

- Emit only the element at the defined index `n`.
- Ignores all but the defined element.

```
----1--2-----3--4---->

elementAt(2)

-------------3------->
```
