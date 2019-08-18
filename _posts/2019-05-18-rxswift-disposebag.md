---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:05
description: "DisposeBag"
layout: post
permalink: rxswift-disposebag
published: true
tags: [Rx, ReactiveX, RxSwift, DisposeBag]
title: "What is a DisposeBag in RxSwift?"
---

## RxSwift: DisposeBag

- Used to avoid memory leaks as the subscription will not be disposed of correctly without.
- `DisposeBag` holds disposables.
- `DisposeBag` allows us not to have to dispose of each subscription individually.
- Used with `.addDisposableTo()` operator which will call `dispose()` on each when the dispose bag is about to be deallocated.

```swift
let disposeBag = DisposeBag()

Observable.of("Chris Sutton", "Henrik Larsson", "Bobo Balde")
	.subscribe {
		print($0)
	}
	.addDisposableTo(disposeBag)
```

- Can manually cause an observable to terminate by cancelling the subscription to it (Not recommended - should use `disposeBag` above).

```
subscription.dispose()
```
