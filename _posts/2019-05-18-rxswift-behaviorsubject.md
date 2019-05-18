---
author: "Liam"
category: "RxSwift"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: link-name
published: false
tags: [tag1, tag2]
title: "title"
---

## RxSwift: Behavior Subject

-- Starts with an initial value and replays it or the latest element to new subscribers.
— Similar to Publish Subjects except, they will replay the latest `.next` event to new subscribers.
— Needs a initial value upon creation - If you can’t think of one use a PublishSubject
— Useful when you want to repopulate a view with the most recent data
— Usage: bind controls in a user profile screen so the latest values can be use to pre-populate the display while the app fetches fresh data.

```
let subject = BehaviorSubject<String>(value: "8 in a row")
```
