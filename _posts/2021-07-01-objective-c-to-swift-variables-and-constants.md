---
author: "Liam"
date: 2020-01-01 00:00:00
description: "Objective-C to Swift"
layout: post
permalink: objc-to-swift-overview
published: false
tags: [objective-c, swift]
title: "Objective-C to Swift Conversion Overview"
---

# Objective-C to Swift

# Variables and Constants

- Swift uses type inference: The type of variables can be inferred therefore the type can be left out of a variable / constant declaration.

e.g:

`var title: String = "Step Into Swift"` becomes `var title = "Step Into Swift"`

| Objective-C | Swift |
|---|---|
| `type name = assignment; or var name: type = assignment` | `var name = assignment` |

## Variables

| | Objective-C | Swift |
|---|---|---|
| String    | `NSString *title = @"Step Into Swift";`   | `var title = "Step Into Swift"` |
| Integer   | `NSInteger numberOfChampionships = 9;`     | `var numberOfChampionships = 9` |
| Boolean   | `BOOL championsAgain = YES;`               | `var championsAgain = true` |

## Constants

| | Objective-C | Swift |
|---|---|---|
| String    | `NSString * const title = @"Step Into Swift";`   | `let title = "Step Into Swift"` |
| Integer   | `const NSInteger numberOfChampionships = 9;`     | `let numberOfChampionships = 9` |
| Boolean   | `const BOOL championsAgain = YES;`               | `let championsAgain = true` |
