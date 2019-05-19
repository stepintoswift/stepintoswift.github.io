---
author: "Liam"
category: "RxSwift"
date: 2019-05-19 00:00:00
description: "What is the Create Operator in RxSwift?"
layout: post
permalink: rxswift-operator-create
published: true
tags: [Rx, ReactiveX, RxSwift, Create, Operators, Operators]
title: "Create Operator"
---

## RxSwift: Create Operator

- Specifies all events that an observable will emit to subscribers.
- Takes a single parameter named `subscribe`.
- Provide the implementation of calling `subscribe` on the Observable.
- `subscribe` parameter is an escaping closure that takes an `AnyObserver` and returns a `Disposable`.
- `AnyObserver` is a generic type that allows you to add values `onto` an observable sequence, which will then be emitted to subscribers.
- Most flexible way to create a custom observable however, you have to remember to send a `.completed` event and also return `Disposable`.

Example:

```swift
Observable<String>.create { observer in
  observer.onNext("Gary Hooper")
  observer.onNext("Tony Stokes")
  observer.onCompleted()
  // No point in .onNext again as we have completed
  // and no more events will be emitted.
  return Disposables.create()
}
```
