---
author: "Liam"
category: "RxSwift"
date: 2019-05-27 00:00:08
description: "Concat Operator"
layout: post
permalink: rxswift-operator-concat
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Concat, Combining]
title: "What is the Concat Operator in RxSwift?"
---

## RxSwift: Concat Operator

`.concat(_:)`

- Chains two or more Observable sequences.
- Concatenates the output of multiple Observables into a single Observable in Observable order.
- First Observable completes followed by the second and so forth.
- If trying to concatenate a "hot" Observable, `concat` will not see it and will not emit.
- Used as a static function or instance method of an Observable.
- If the inner Observable emits an `error`, the result Observable emits `error` and terminates.
- N.B: Observable sequences are strongly typed so you can only concatenate sequences where the elements are the same type.
- If you want to add to the start of an Observable, use the [`.startWith(_:)`]({% post_url 2019-05-27-rxswift-operator-startwith %}) operator.

```
--T------E-----N----------------->
-I--N------A----R----O-------W--->

concat()

--T------E-----N-I-N-A-R-O-W----->
```
