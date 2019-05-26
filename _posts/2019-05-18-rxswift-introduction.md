---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "An introduction to ReactiveX"
layout: post
permalink: rxswift-introduction-to-reativex
published: true
tags: [Rx, ReactiveX, RxSwift, Sequences, Operators]
title: "What is ReactiveX?"
---

## RxSwift: An introduction to ReactiveX

- ReactiveX is a library for composing asynchronous and event based programs by using observable sequences.
- It extends the observer pattern.
- Provides a collection of operators with which you can filter, select, transform, combine and compose Observables.
- Everything is a sequence or something that works with a sequence.

Things you can do:

- React to a property changing:

```swift
let disposeBag = DisposeBag()

let homeTeamScore = BehaviorSubject<Int>(value: 0)

homeTeamScore.subscribe(onNext: { [weak self] score in
  self?.playSound(.goal)
})
.disposed(by: disposeBag)

homeTeamScore.onNext(1)
```

- React to a button tap (Using RxCocoa)

```swift
signInButton
  .rx.tap
  .asObservable()
  .subscribe(onNext: { [unowned self] in
		self.signIn() })
  .disposed(by: disposeBag)
```
