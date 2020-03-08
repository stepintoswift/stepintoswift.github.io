---
author: "Liam"
date: 2020-03-08 00:00:00
description: "Short-circuit Evaluation"
layout: post
permalink: short-circuit-evaluation
published: true
tags: [short circuiting, short-circuit evaluation]
title: "What is Short-circuit Evaluation?"
---

# Short-circuit Evaluation

## What is Short-circuit Evaluation
- When part of an evaluation is determined, the rest of the statement does not get evaluated.

## Grammar
- "The logical `AND` and logical `OR` operators use short-circuit evaluation when considering their expressions."

## Usage

### Logical Operators

With a logical `AND` operator, given the first value is `false`, there is no way for the expression to pass so we do not evaluate the rest of the conditions. This is known as short-circuit evaluation.

```
let pitchIsPlayable = false
let haveEnoughPlayers = true
let haveReferee = true

if pitchIsPlayable && haveEnoughPlayers && haveReferee { ... }
```

### Optional Binding

Instead of nesting `if` statements we can move the conditional logic to the same line as where we optionally bind. If the boolean value at the start of the binding line is false, the rest of the line does not get evaluated.

```
if pitchIsPlayable, let players = wrappedPlayers { ... }
```
