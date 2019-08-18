---
author: "Liam"
category: "RxSwift"
date: 2019-07-22 00:00:14
description: "Sample Operator"
layout: post
permalink: rxswift-operator-sample
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Sample, Filtering]
title: "What is the Sample Operator in RxSwift?"
---

## RxSwift: Sample Operator

`.sample()`

- Emits the most recent element emitted by an Observable within a periodic time interval.
- Similar to `withLatestFrom`, however sample takes a trigger Observable as a parameter.
- When the tigger Observable ends, the most recent element from the source Observable will emit.

```
--1--------2---3----4--------5------>
------a-----b-c-------------d----|--->

sample

------1-----2---------------4----5-->
```
