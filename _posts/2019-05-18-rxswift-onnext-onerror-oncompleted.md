---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:04
description: "onNext, onCompleted, onError"
layout: post
permalink: rxswift-onnext-oncompleted-onerror
published: true
tags: [Rx, ReactiveX, RxSwift, onNext, onCompleted, onError]
title: "RxSwift onNext, onCompleted, onError, ohMy!!"
---

## RxSwift: onNext, onCompleted, onError

### onNext
- Called by the Observable when it emits an item.
- Takes as a parameter the item emitted by the Observable.
- Calls are referred to as `emissions`.

### onError
- Called to indicate that the Observable has failed to generate the expected data or has encountered an error.
- Observable will terminate.
- No more calls to `onNext` or `onCompleted`.
- Takes a parameter an indication of what caused the error.
- Calls are referred to as `notifications`.

### onCompleted
- Called after the Observable has called `onNext` for a final time (If no errors have occurred).
- Calls are referred to as `notifications`.
