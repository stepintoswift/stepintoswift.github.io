---
author: "Liam"
category: "RxSwift"
date: 2019-05-26 00:00:02
description: "Transforming Operators"
layout: post
permalink: rxswift-operators-transforming
published: true
tags: [Rx, ReactiveX, RxSwift, Transforming, Operators]
title: "What are the Transforming Operators in RxSwift?"
---

## RxSwift: Common Transforming Operators

Observers emit elements individually, but you'll frequently want to work with collections.
Use the below operators to transform those individual elements into a collection:

- [`.toArray()`]({% post_url 2019-05-27-rxswift-operator-toarray %})
- [`.map {}`]({% post_url 2019-05-27-rxswift-operator-map %})
- [`.mapWithIndex {}`]({% post_url 2019-05-27-rxswift-operator-mapwithindex %})
- [`.flatMap {}`]({% post_url 2019-05-27-rxswift-operator-flatmap %})
- [`.flatMapLatest {}`]({% post_url 2019-05-27-rxswift-operator-flatmaplatest %})
- [`.scan {}`]({% post_url 2019-05-27-rxswift-operator-scan %})
