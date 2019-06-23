---
author: "Liam"
date: 2019-06-23 00:00:01
description: "BindTo Operator"
layout: post
permalink: rxswift-rxcocoa-bindto
published: true
tags: [RxSwift, RxCocoa, BindTo]
title: "What is the bindTo operator in RxCocoa?"
---

# RxSwift: BindTo

- Special and tailored version of `subscribe`
- No side effects or special cases
- Bind user interface to underlying data and other things such as a certain observable triggering a subject to perform a background task.
- To bind an observer to another entity, the receiver must conform to observer type. i.e: a Subject that can process values but also written to.

```
search.map { "\($0.score)" }
      .bindTo(scoreLabel.rx.text)
      .addDisposableTo(disposeBag)
```
