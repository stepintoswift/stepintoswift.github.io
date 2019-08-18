---
author: "Liam"
date: 2019-08-19 00:00:02
description: "Short Circuiting"
layout: post
permalink: short-circuiting
published: false
tags: [short circuiting]
title: "What is a short circuiting?"
---

## What is short circuiting?

- Occurs when checking predicate logic.
- E.g: AND operator && -> If the left side of an operator fails, the rest of the predicate will not be checked. No way for the expression to be true.

```
if emailIsNotEmpty && passwordIsNotEmpty {
  ...
}
```

- Also used with an `if let` statement.
- If short circuiting did not kick in, the app could crash depending on the latter checks.

```
if let value = array.first, value != 100 {
  ...
}
```
