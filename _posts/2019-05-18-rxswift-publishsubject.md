---
author: "Liam"
category: "RxSwift"
date: 2019-06-10 00:00:07
description: "PublishSubject"
layout: post
permalink: rxswift-publishsubject
published: true
tags: [Rx, ReactiveX, RxSwift, Subjects, PublishSubject]
title: "What is a PublishSubject in RxSwift?"
---

## RxSwift: Publish Subject

- Starts empty and only emits new elements to subscribers.
- Useful when you want subscribers to be notified of new events from the point at which they subscribed until they either unsubscribe or termination (`.completed` / `.error`).
- Will emit stop event to new subscribers and no longer emit `.next` events.
- Will re-emit stop event to future subscribers.
- Use case: Modelling time-sensitive data.

```swift
let subject = PublishSubject<String>()
subject.onNext("Champions again as you know!")
```
