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

# Enums

## Objective-C

- Objective-C enums are limited to Integer types

```
typedef NS_ENUM(NSInteger, CupType) {
  premierLeague,
  leagueCup,
  europaLeague
}
```

## Swift

- Swift enums are not limited to `Integers` like Objective-C `enums`

```
  enum cupType {
    case premierLeague
    case leagueCup
    case europaLeague
  }
```
