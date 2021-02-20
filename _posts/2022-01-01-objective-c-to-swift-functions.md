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

# Functions

## Objective-C

```
- (void)helloDortmund() {
  NSLog(@"Hello Dortmund");
}

[self helloDortmund];
```

```
- (NSString*)germanKings {
  return @"Dortmund!";
}

NSString *kings = [self germanKings];
```

```
- (BOOL)isPlaying {
  return YES;
}

BOOL inProgress = [self isPlaying];
```

```
- (void)printTeamName: (NSString*)teamName {
  NSLog(@"Team name %@", teamName);
}

[self printTeamName: "BVB"];
```

```
- (void)printPlayerDetailsFor:(NString*)name number:(NSInteger)number {
  NSLog(@"Player Name %@", name);
  NSLog(@"Squad Number %@", number)
}

[self printPlayerDetailsFor:@"Solskjaer" number:20];
```

## Swift

```
func helloDortmund() {
  print("Hello Dortmund!")
}

helloDortmund()
```

```
func germanKings() -> String {
  return "Dortmund!"
}

let kings = germanKings()
```

```
func isPlaying() -> Bool {
  return true
}

print(isPlaying())
```

```
func printTeamName(teamName: String) {
  print("Team Name: \(teamName)")
}

printTeamName(teamName: "BVB")
```

```
func printTeamName(for teamName: String) {
  print("Team Name: \(teamName)")
}

printTeamName(for: "Dortmund")
```

```
func printTeamName(_ teamName: String) {
  print("Team Name: \(teamName)")
}

printTeamName("BVB")
```

```
func printPlayerDetails(for name: String, number: Int) {
  print("Player Name: \(name)")
  print("Squad Number: \(number)")
}

printPlayerDetails(for "Solskjaer", number: 20)
```
