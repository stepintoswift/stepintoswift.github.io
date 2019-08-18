---
author: "Liam"
date: 2019-08-05 00:00:03
description: "RxSwift: Driver"
layout: post
permalink: rxswift-rxcocoa-driver
published: true
tags: [RxSwift, RxCocoa, Driver]
title: "What is a Driver in RxCocoa?"
---

# RxSwift: Driver

- Special observable
- Cannot error layout.
- All processes ensured to execute on the main thread.
- Go from: a single observable that updates the entire UI to `bindTo` and reuse the same observable across the viewController.

```
result.map { "\($0.score)" }
      .drive(scoreLabel.rx.text)
      .addDisposableTo(disposeBag)
```
