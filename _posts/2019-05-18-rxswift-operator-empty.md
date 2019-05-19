---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: variable
published: false
tags: [variable var]
title: "Variable"
---

## RxSwift: `empty` operator

— Useful when you want to return an observable that immediately terminates or intentionally has zero values.
— Emits no elements followed by a `.completed` event

```swift
let observable = Observable<Void>.empty
```
