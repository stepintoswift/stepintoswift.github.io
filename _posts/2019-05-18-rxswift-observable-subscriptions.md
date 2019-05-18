---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: variable
published: false
tags: [variable var]
title: "Variable"
---

## RxSwift: Subscribing to observables

— Observables will NOT send events until they have a subscriber.
— It is the subscription that triggers an observable to begin emitting events until `.error` or `.completed`
— Observing an observable is known as subscribing.
— Subscribe takes an escaping closure that takes an `event` of the supplied typed (that doesn’t return anything).
— Subscribe returns a `Disposable`.

```
let lotteryNumberOne = 1
let lotteryNumberTwo = 2
let lotteryNumberThree = 3

let observable = Observable.of(lotteryNumberOne, lotteryNumberTwo, lotteryNumberThree)

observable.subscribe { element in
	print(element)
}

// next(1)
// next(2)
// next(3)
// completed
```

— Above emits next events, the below will unwrap the optional elements and produce the value from within the element.

```
...
observable.subscribe(onNext: { lotteryNumber
	print(lotteryNumber)
})

// 1
// 2
// 3
// NO completed event
```