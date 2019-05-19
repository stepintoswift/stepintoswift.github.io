---
author: "Liam"
category: "RxSwift"
date: 2019-05-19 00:00:01
description: "What is the Defer Operator in RxSwift?"
layout: post
permalink: rxswift-operator-defer
published: true
tags: [Rx, ReactiveX, RxSwift, Defer, Operators, Operators]
title: "Defer Operator"
---

## RxSwift: Defer Operator

- Defers execution until observer subscription.
- Waits until an observer subscribes to it.
- Generates an `Observable`, typically with an observable factory.
- Different to `.just` which executes before creating the Observable.
