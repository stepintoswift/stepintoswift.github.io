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

## RxSwift: `never` operator

— Creates an observable that does not emit anything and never terminates
— Represents infinite duration.
— When subscribed to, the `onNext` nor the `onCompleted` ever emit.

```
let observable = Observable<Any>.never()
```
