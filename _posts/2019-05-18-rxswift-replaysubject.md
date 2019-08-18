---
author: "Liam"
category: "RxSwift"
date: 2019-06-10 00:00:09
description: "ReplaySubject"
layout: post
permalink: rxswift-replaysubject
published: true
tags: [Rx, ReactiveX, RxSwift, Subjects, ReplaySubject]
title: "What is a ReplaySubject in RxSwift?"
---

## RxSwift: ReplaySubject

- Initialised with a buffer size and will maintain a buffer of elements up to that size and replay it to new subscribers.
- Useful when you want to show more than the latest value that a `BehaviorSubject` would provide.
- Will temporarily cache or buffer the latest elements it emits up to a specified size.
- Will then replay that buffer to new subscribers.
- Beware that buffer is stored in memory which may cause issues if using images. Large buffers may use up a lot of memory. Also, array will be emitted as such so watch for the size of image based arrays.
- Initialised using the type methods `create(bufferSize:)`.

```swift
let subject = ReplaySubject<String>.create(bufferSuze: 8)
```

- `ReplayMany` is an internal type that is used to create replay subjects. May see this in an error message if you do not dispose of your `ReplaySubject` correctly.
