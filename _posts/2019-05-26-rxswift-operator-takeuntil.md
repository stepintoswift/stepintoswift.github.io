---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:11
description: "TakeUntil Operator"
layout: post
permalink: rxswift-operator-takeuntil
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, TakeUntil]
title: "What is the TakeUntil Operator in RxSwift?"
---

## RxSwift: TakeUntil Operator

`TakeUntil(trigger) `

- Keep taking until some `trigger` observable emits an element.
- Emit nothing after the `trigger` observable has emitted an element.
- Can be used to dispose of a subscription instead of adding to a dispose bag.

```
----7--9-----1--4---->
----------0----0----->

takeUntil(trigger)

----7--9------------->
```

```
let subject = PublishSubject<String>()
let trigger = PublishSubject<String>()

subject.takeUntil(tigger).subscribe(onNext: ....)
```
