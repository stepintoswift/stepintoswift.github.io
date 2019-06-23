---
author: "Liam"
date: 2019-06-23 00:00:02
description: "RxSwift: Units"
layout: post
permalink: rxswift-rxcocoa-units
published: true
tags: [RxSwift, RxCocoa, Units]
title: "What are Units in RxCocoa?"
---

# RxSwift: Units

- A group of classes, which are specialised observables, that allow for easier to write and simpler code, especially when working with UI.

Features:
- Units cannot error out.
- Units are observed on the main scheduler.
- Units subscribe on the main scheduler.
- Units share side effects.

- Units exist to ensure user interface always has something to display and that the displayed data is always treated in the correct way so the UI can handle it.


2 main component parts of the Units framework:
- [`ControlProperty`]({% post_url 2019-06-23-rxswift-rxcocoa-controlproperty %}) & [`ControlEvent`]({% post_url 2019-06-23-rxswift-rxcocoa-controlevent %})
- [`Driver`]({% post_url 2019-06-23-rxswift-rxcocoa-driver %})
