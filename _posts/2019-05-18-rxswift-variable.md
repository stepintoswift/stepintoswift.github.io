---
author: "Liam"
category: "RxSwift"
date: 2019-05-19 00:00:10
description: "What is a variable in RxSwift"
layout: post
permalink: rxswift-variable
published: true
tags: [Rx, ReactiveX, RxSwift, Subjects, Variable]
title: "RxSwift: Variable"
---

## RxSwift: Variables

- Wraps a `BehaviorSubject` and stores its current state.
- Can access the current value via `value` property.
- Use `value` to set a new element onto a variable (Don’t use `onNext(_:)`).
- Because it wraps a `BehaviorSubject` it is create with an initial value and it will replay its initial value to new subscribers.
- To access a variables `BehaviorSubject` call `asObservable()`.
- Guaranteed NOT to emit an error.
- Can listen for error events but cannot add one.
- Will also automatically `complete` when it is about to be deallocated so you do not and cannot manually add `.completed`.
- Like any other subject it can be subscribed to by an observable to be reacted to when a new `.next` event is emitted.
- Useful for one off needs such as checking the current value without subscribing to receive updates.

```swift
var variable = Variable("James Forrest")
variable.value = "Scott Brown"
```
