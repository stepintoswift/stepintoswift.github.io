---
author: "Liam"
category: "RxSwift"
date: 2019-06-10 00:00:08
description: "BehaviorSubject"
layout: post
permalink: link-name
published: true
tags: [Rx, ReactiveX, RxSwift, Subjects, BehaviorSubject]
title: "What is a BehaviorSubject in RxSwift?"
---

## RxSwift: BehaviorSubject

- Similar to a `PublishSubject` except, it will replay the latest `.next` event to new subscribers.
- Needs a initial value upon creation - If you can’t think of one use a PublishSubject
- Starts with an initial value and replays it or the latest element to new subscribers.
- Useful when you want to repopulate a view with the most recent data.

```swift
let subject = BehaviorSubject<String>(value: "8 in a row!")
```
