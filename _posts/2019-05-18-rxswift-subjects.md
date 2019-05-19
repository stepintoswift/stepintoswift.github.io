---
author: "Liam"
category: "RxSwift"
date: 2019-05-19 00:00:06
description: "What is a Subject in RxSwift?"
layout: post
permalink: rxswift-subjects
published: true
tags: [Rx, ReactiveX, RxSwift, Subjects, PublishSubject, BehaviorSubject, ReplaySubject, Variable]
title: "Subjects"
---

## RxSwift: Subjects

- Can act as both an `Observable` and as an `Observer`.
- `.onNext(_:)` puts a new element onto the subject.
- Need subscribers for events to happen.
- Every subject type, once terminated will re-emit its stop event to future subscribers.

### 4 different types of Subjects:

1. **PublishSubject:**
Starts empty and only emits new elements to subscribers.
2. **BehaviorSubject:**
Starts with an initial value and replays it or the latest element to new subscribers.
3. **ReplaySubject:**
Initialised with a buffer size and will maintain a buffer of elements up to that size and replay it to new subscribers.
4. **Variable:**
Wraps a `BehaviorSubject`. Preservers its current value as state and replays only the latest/initial value to new subscribers.
