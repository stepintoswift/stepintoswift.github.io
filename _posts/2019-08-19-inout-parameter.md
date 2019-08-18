---
author: "Liam"
date: 2019-08-19 00:00:00
description: "Inout parameter"
layout: post
permalink: in-out-parameter
published: false
tags: [inout, in, out]
title: "What is an inout parameter?"
---

## What is an inout parameter

- Value is passed into the function, it is then modified by the function, and is passed back out of the function to replace the original value.
- Pass-by-value-and-copy-back NOT pass-by-reference.
- Every inout parameter needs a `&` prefix.
- Must pass in a variable.
- If you pass in an `UnsafeMutablePointer` as a parameter but now we are passing by reference. Not recommended to use this if possible.

```
func increment(value: inout Int) {
  value += 1
}

var value = 0
increment(value: &value)
```
