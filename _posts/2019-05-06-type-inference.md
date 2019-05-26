---
author: "Liam"
date: 2019-05-06 00:00:12
description: "Type Inference"
layout: post
permalink: type-inference
published: true
tags: [type inference]
title: "What is Type Inference?"
---

## Type Inference

Simply put, the type of an object can be inferred from its value.

The full (long) way of declaring a String for instance would be:

```swift
let song: String = "Champions again as you know!"
```

Swift is smart enough however to know that `song` should be a `String` and we therefore can remove the type and simply put:

```swift
let song = "Champions again as you know!"
```

This can be used on any type, such as `Int`:

Full declaration:
```swift
let titlesInARow: Int = 8
```

With type Inference:

```swift
let titlesInARow = 8
```

We do however need to give the object a type if we do not give it a default value as Swift does not know what the type will be:
```
let newSigning: String
```

Swift will also what to know the type if there is any ambiguity:

```swift
let distance = 2.3

var newDistance: Float = result
```

The above will not compile with the error `Cannot convert value of type 'Double' to specified type 'Float'`. Swift will infer that the type of distance is `Double` so we must give it a type upon declaration.

```swift
let distance: Float = 2.3

var newDistance: Float = result
```
