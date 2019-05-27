---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:09
description: "Merge Operator"
layout: post
permalink: rxswift-operator-merge
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Merge, Combining]
title: "What is the Merge Operator in RxSwift?"
---

## RxSwift: Merge Operator

`.merge()`

- Combines multiple Observables into a single Observable.
- Subscribes to each Observable sequence it receives and emits the elements as soon as they arrive.
- No predefined order.
- `error` in any source sequence results in replaying of the error followed by termination of the destination sequence.

```
-----1--2---3------5---7------------>
----------------4----6----8--------->

merge

-----1--2---3---4--5-6-7--8-------->

```
