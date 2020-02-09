---
author: "Liam"
date: 2020-02-10 00:00:00
description: "Typealias"
layout: post
permalink: typealias
published: true
tags: [typealias]
title: "What is a typealias?"
---

# Typealias

## What is a Typealias?

- Adds a named alias for an existing type
- Does not create a new type, it just refers to the existing type
- You can use this named alias instead / as well as of the existing type name
- Grammar: "A typealias definition"

## Creating a Typealias

- A typealias takes the form:

```
    typealias name = existing type
```

## Using a Typealias

- Typealias' are useful to rename a type that may be complex to read each time, or you want to redefine the name of.
- The existing type remains the same, this is just an alias for the existing type.

Example: Typealias `String` and for use as a `Key`

```
typealias Key = String
let analyticsKey: Key
```

Example: Typealias `Int` and use as an `Identity`

```
typealias Identity = Int
let identity: Identity = 0
```

Example: Typealias a completion handler to make the completion handler parameter types more readable

```
typealias ImageLoadingCompletedHandler = (() -> Void)

func loadImage(imageUrl: URL?, onCompleted: ImageLoadingCompletedHandler? = nil) {
  ...
```

Example: Typealias multiple protocols so that the type conforms to the typealias

```
typealias Element = Equatable & CustomStringConvertible
```
