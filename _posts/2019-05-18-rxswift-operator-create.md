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

## RxSwift: `create` operator

— Specify all events that an observable will emit to subscribers
— Takes a single parameter named `subscribe`
— Provide the implementation of calling `subscribe` on the observable. It defines all the events that will be emitted to subscribers
— `subscribe` parameter is an escaping closure that takes an `AnyObserver` and returns a `Disposable`
— `AnyObserver` is a generic type that allows for adding values `onto` an observable sequence, which will then be emitted to subscribers.
— Most flexible way to create a custom observable however have to remember to send a `.completed` event and also return `Disposable`