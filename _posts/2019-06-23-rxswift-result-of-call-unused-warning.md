---
author: "Liam"
date: 2019-06-23 00:00:00
description: "Rx Warning: Result of call to subscription is unused"
layout: post
permalink: rxswift-result-of-call-unused-warning
published: true
tags: [RxSwift, DisposeBag, Warning]
title: "Result of call to subscribe(onNext: onError: onCompleted: onDisposed:) is unused"
---

# RxSwift: Result of call to subscribe(onNext: onError: onCompleted: onDisposed:) is unused - warning

- The solution is simply to add the subscription to a DisposeBag by adding `.disposed(by: disposeBag)` at the end of the subscription.


```
viewController
            .actions
            .subscribe(onNext: { [unowned self] actions in
                switch actions {
                case let .showLogin():
                    self.showLogin()
                }
            })
            .disposed(by: disposeBag)
```

- This will cancel and dispose of the subscription whenever the view controller is released.
- Prevents wasting resources but also avoids unexpected events or other side effects when subscriptions are not disposed.
