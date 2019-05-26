---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:08
description: "What is the SkipUntil Operator in RxSwift?"
layout: post
permalink: rxswift-operator-skipuntil
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, SkipUntil]
title: "SkipUntil Operator"
---

## RxSwift: SkipUntil Operator

`skipUntil(trigger)`

- Keep skipping until some `trigger` observable emits an element.
- Emit everything after the `trigger` observable has emitted an element.

```
----7--9-----1--4---->
----------0----0----->

skipUntil(trigger)

-------------1--4---->
```

```
let subject = PublishSubject<String>()
let trigger = PublishSubject<String>()

subject.skipUntil(tigger).subscribe(onNext: ....)
```