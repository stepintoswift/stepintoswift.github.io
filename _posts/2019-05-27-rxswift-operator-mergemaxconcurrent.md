---
author: "Liam"
category: "RxSwift"
date: 2019-07-08 00:00:10
description: "Merge MaxConcurrent Operator"
layout: post
permalink: rxswift-operator-mergemaxconcurrent
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Merge MaxConcurrent, Combining]
title: "What is the Merge MaxConcurrent Operator in RxSwift?"
---

## RxSwift: MergeMaxConcurrent Operator

`.merge(maxConcurrent:)`

- Keeps subscribing to incoming sequences until it reaches the max concurrent limit.
- Same functionality as the [`merge`](% post_url 2019-05-27-rxswift-operator-merge %) operator, concatenating multiple
Observables, however maxConcurrent parameter allows a limit of the number of subscribe-able Observables.
- Useful for resource intensive situations like making a lot of network requests and limiting the number of concurrent outgoing connections.

```
-----1--2---3------5---7------------>
----------------4----6----8--------->
-------------------9------------10-->

merge(maxConcurrent: 2)

-----1--2---3---4--5-6-7--8-------->

```
