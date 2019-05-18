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

## RxSwift: `DisposeBag`

— `DisposeBag` allows us not to have to dispose of each subscription individually.
— `DisposeBag` holds disposables
— Used with `.addDisposableTo()` operator which will call `dispose()` on each when the dispose bag is about to be deallocated.
— Used to avoid memory leaks as the subscription will not be disposed of correctly without.

```
let disposeBag = DisposeBag()

Observable.of("Chris Sutton", "Henrik Larsson", "Bobo Balde")
	.subscribe {
		print($0)
	}
	.addDisposableTo(disposeBag)
```

— Can manually cause an observable to terminate by cancelling the subscription to it (not recommended, use disposeBag’s above)

```
subscription.dispose()
```