---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:01
description: "Observables"
layout: post
permalink: rxswift-observables
published: true
tags: [Rx, ReactiveX, RxSwift, Observable, Observer]
title: "What is a Rx Observable?"
---

## RxSwift: Observables

- An _Observer subscribes_ to an _Observable_.
- The _Observer_ reacts to what the _Observable_ emits.
- Rx Observables are intended for composing flows and sequences of asynchronous data.
- An Observable is just a sequence with special abilities. For example, it is asynchronous.
- Observable is a sequence definition that must be subscribed to for anything to really happen.
- Observables must be defined as being a specific type if the type cannot be inferred.
- Observables produce events. We say that they are “emitting”.
- Observables emit `next` events until an `error` event or `completion` event occurs.
- When an `error` or `completion` event occurs, this results in termination and no more events get emitted.
- Events can contain:
    * Values (Numbers, instances of a custom type).
    * Gesture recognisers (`Tap`).

Examples of creating observable sequences:

```swift
let championsSequence = Observable.just("Celtic")

let titlesInARow = Observable.from([1,2,3,4,5,6,7,8])
```

Example of subscribing to an observable:

```swift
let disposeBag = DisposeBag()

let champions = Observable.just("Celtic!")

champions.subscribe(onNext: { [weak self] champs in
  print(champs)
})
.disposed(by: disposeBag)
```

Example of a tap event:

```swift
signInButton
  .rx.tap
  .asObservable()
  .subscribe(onNext: { [unowned self] in
		self.signIn() })
  .disposed(by: disposeBag)
```
