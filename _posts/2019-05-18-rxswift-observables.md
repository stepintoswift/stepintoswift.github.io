---
author: "Liam"
date: 2019-05-18 00:00:00
description: "description"
layout: post
permalink: link-name
published: false
tags: [tag1, tag2]
title: "title"
---

## Observables

- An _Observer subscribes_ to an _Observable_.
- The _Observer_ reacts to what the _Observable_ emits.
- Rx Observables are intended for composing flows and sequences of asynchronous data.
- An Observable is just a sequence with special abilities. For example, it is asynchronous.
- Observable is a sequence definition that must be subscribed to for anything to really happen.
- Observables must be defined as being a specific type if the type cannot be inferred.
- Observables produce events. We say that they are “emitting”.
- Events can contain:
    * Values (Numbers, instances of a custom type).
    * Gesture recognisers (`Tap`).
- Observables emit `next` events until an `error` event or `completion` event occurs.
- When an `error` or `completion` event occurs, this results in termination and no more events get emitted.
- RX methods are referred to as operators.
