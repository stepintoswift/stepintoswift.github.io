---
author: "Liam"
date: 2019-06-03 00:00:09
description: "Variadic Parameter"
layout: post
permalink: variadic-parameter
published: true
tags: [variadic]
title: "What is a Variadic Parameter?"
---

## Variadic Parameter

- Accepts zero or more values of a specific type.
- Create by inserting three periods after the parameters type name.
- Values of variadic parameter are accessible within the function body through an array of the defined type.
- A function can only have ONE variadic parameter

```swift
func sum(_ numbers: Int...) -> Int {
    var total: Int = 0

    for number in numbers {
        total += number
    }

    return total
}

sum(1, 2, 3, 4, 5)		
// Returns 15 - Sum of the numbers
```
