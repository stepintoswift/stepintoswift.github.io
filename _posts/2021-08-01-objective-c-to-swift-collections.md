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

# Collections

## Array

### Objective-C

#### Mutable Arrays

```
NSMutableArray *players = [NSMutableArray new];

[players addObject: @"Ajer"];
```

```
NSMutableArray<NSString *> *players = [NSMutableArray new];
```

#### Immutable Arrays

```
NSArray *players = @[@"Forrest", @"Brown", @"Christie"];
```

### Swift

#### Mutable Arrays

```
var players = [String]()

players.append("Ajer")
```

```
var players = Array<String>()
```

#### Immutable Arrays

```
let players = ["Forrest", "Brown", "Christie"]
```

## Dictionary

### Objective-C

```
NSDictionary *squadNumbers = @{
  @"Forrest": @49,
  @"Brown": @8,
  @"Christie": @17
};
```

### Swift

```
let squadNumbers = [
  "Forrest": 49,
  "Brown": 8,
  "Christie": 17
]
```
