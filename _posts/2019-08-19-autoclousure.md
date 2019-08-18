---
author: "Liam"
date: 2019-08-26 00:00:01
description: "Autoclosure"
layout: post
permalink: autoclosure
published: false
tags: [autoclosure, closure]
title: "What is an autoclosure?"
---

## What is an autoclosure?

- The `@autoclosure` attribute is used to tell the compiler that it should wrap an argument in a closure expression.
- Basically we annotate a function parameter with `@autoclosure`.
- Instead of passing a closure as a parameter to a function, if the parameter is annotated with `@autoclosure` it can be passed as if it is a `String`.

### Without autoclosure

- We have to wrap the code we want to call in `{ }` at the call site.

```
// penaltyTakers ["Scott Brown", "James Forrest", "Kieran Tierney"]

func takePenalty(player penaltyTaker: () -> String) {
    print("Penalty taker \(penaltyTaker())!")
}

takePenalty(player: { penaltyTakers.remove(at: 0) } )

// Prints "Penalty taker Scott Brown!"
```

### With autoclosure

- Adding `@autoclosure` in front of the closure parameter type.
- No need for `{ }` at the call site.

```
// penaltyTakers ["Scott Brown", "James Forrest", "Kieran Tierney"]

func takePenalty(player penaltyTaker: @autoclosure () -> String) {
    print("Penalty taker \(penaltyTaker())!")
}

takePenalty(player: penaltyTakers.remove(at: 0) )

// Prints "Penalty taker Scott Brown!"
```
