---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: link-name
published: false
tags: [tag1, tag2]
title: "title"
---

## RxSwift: Publish Subject

-- Starts empty and only emits new elements to subscribers.
— Useful when you want subscribers to be notified of new events from the point at which they subscribed until they either unsubscribe or termination (`.completed` / `.error`)
— Will emit stop event to new subscribers and no longer emit `.next` events
— Will re-emit stop event to future subscribers
— Usage: modelling time-sensitive data.

```swift
let subject = PublishSubject<String>()
subject.onNext("Champions again as you know")
```
