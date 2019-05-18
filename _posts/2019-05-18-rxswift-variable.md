---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: link-name
published: false
tags: [rxswift, variable, subject]
title: "RxSwift: Variable"
---

## RxSwift: Variables

— Wraps a `BehaviorSubject` and stores its current state
— Can access current value via `value` property
— Use `value` to set a new element onto a variable (Don’t use `onNext(_:)`)
— Because it wraps a `BehaviorSubject` it is create with an initial value and it will replay its initial value to new subscribers.
— To access a variables `BehaviorSubject` call `asObservable()`
— Guaranteed NOT to emit an error
  — can listen for error events but cannot add one
— Will also automatically complete when it is about to be deallocated so you do not and cannot manually add `.completed`.
— Can subscribe tot hem as observables to be able to react when a new `.next` event is emitted, just like any other subject
— Useful for one off needs such as checking the current value without subscribing to receive updates.

```
var variable = Variable("James Forrest")
variable.value = "Scott Brown"
```
