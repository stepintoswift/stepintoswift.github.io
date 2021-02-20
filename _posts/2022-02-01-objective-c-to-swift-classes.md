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

# Classes

## Objective-C

```
@interface Player: NSObject

@property(strong) NSString *name;

// instance method
- (BOOL)isInjured;

// Static method
+ (void)printPlayerDetails;

@end

@implementation Player

@property(nonatomic, readonly) NSString *address;

- (BOOL)isInjured {
  return YES
}

+ (void)printPlayerDetails {
  NSLog("Name %@", self.name);
  NSLog("Address %@", self.address);
}

@end
```

## Swift

```
class Player {
  var name: String
  private var address: String

  init(name: String, address: String) {
    self.name = name
    self.address = address
  }

  func isInjured() -> Bool {
    return true
  }

  class func printPlayerDetails() {
    print("Name: \(name)")
    print("Address: \(address)")
  }
}
```
