---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:00
description: "What are the Filtering Operators in RxSwift?"
layout: post
permalink: rxswift-filtering-operators
published: true
tags: [Rx, ReactiveX, RxSwift, Filtering, Operators]
title: "Filtering Operators"
---

## RxSwift: Common Filtering Operators

### Distinct Operators
- `.distinctUntilChanged()`
- `.distinctUntilChanged(_:)`

### Ignoring Operators
- `.ignoreElements()`
- `.elementAt(n)`
- `.filter()`

### Skipping Operators
- `.skip(n)`
- `.skipWhile()`
- `.skipUntil(trigger)`
- `.skipWhileWithIndex(n)`

### Taking Operators
- `.take(n)`
- `.takeWhile()`
- `.takeWhileWithIndex(n)`
- `.takeUntil()`
