---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "What is ReactiveX?"
layout: post
permalink: introduction-to-rx
published: true
tags: [RX, ReactiveX, RxSwift, Sequences, Operators]
title: "Introduction to Rx"
---

## Introduction to Rx

- ReactiveX is a library for composing asynchronous and event based programs by using observable sequences.
- It extends the observer pattern.
- Provides a collection of operators with which you can filter, select, transform, combine and compose Observables.
- Everything is a sequence or something that works with a sequence.

Things you can do:

- React to a property changing:

```
let homeTeamScore = BehaviorSubject<Int>(value: 0)
let disposeBag = DisposeBag()

homeTeamScore.subscribe(onNext: { [weak self] score in
  self?.playSound(.goal)
})
.disposed(by: disposeBag)

homeTeamScore.onNext(1)
```

- React to a button tap (Using RxCocoa)

```
signInButton
  .rx.tap
  .asObservable()
  .subscribe(onNext: { [unowned self] in
		self.signIn() })
  .disposed(by: disposeBag)
```
