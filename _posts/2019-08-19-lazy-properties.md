---
author: "Liam"
category: "Swift"
date: 2019-08-19 00:00:01
description: "Lazy Properties"
layout: post
permalink: lazy-stored-properties
published: true
tags: [lazy, properties]
title: "What is a lazy stored property?"
---

## What is a lazy stored property?

- Used to defer expensive computation until property is used for the first time.
- Must always be declared as a `var` as its initial value might not be set until after initialisation completes.
- Add the `lazy` key word in front of the `var` keyword.
- `: Type` followed by closure syntax.
- `()` on the end of the closure.
- Stored properties and lazy stored properties cannot be defined in an extension.

```
lazy var something: Int {
  // Carry out some expensive computation

  return result
}()
```
