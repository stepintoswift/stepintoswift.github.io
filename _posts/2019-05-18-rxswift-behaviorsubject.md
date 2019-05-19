---
author: "Liam"
category: "RxSwift"
date: 2019-05-19 00:00:08
description: "What is a BehaviorSubject in RxSwift?"
layout: post
permalink: link-name
published: true
tags: [Rx, ReactiveX, RxSwift, Subjects, BehaviorSubject]
title: "BehaviorSubject"
---

## RxSwift: BehaviorSubject

- Similar to a `PublishSubject` except, it will replay the latest `.next` event to new subscribers.
- Needs a initial value upon creation - If you can’t think of one use a PublishSubject
- Starts with an initial value and replays it or the latest element to new subscribers.
- Useful when you want to repopulate a view with the most recent data.

```swift
let subject = BehaviorSubject<String>(value: "8 in a row!")
```
