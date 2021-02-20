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

# Control Structures

Overview of differences
- Parenthesis optional in Swift: `( )`
- Braces mandatory in Objective-C: `{}`
- Boolean conditions

## if statement

### Objective-C

```
NSInteger nineInRow = 9;

if(nineInRow >= 9) {
  NSLog(@"Champions again ole ole!");
} else {
  NSLog(@"Catch up!");
}
```

### Swift
```
var nineInRow = 9

if nineInRow >= 9 {
  print("Champions again ole ole!")
} else {
  print("Catch up!")
}
```

## for loops

### Objective-C

```
for(NSInteger championships = 1; championships <= 9; championships++) {
  NSLog(@"Champions again ole ole!");
}
```

```
NSArray *players @["Brown", "Forrest", "Ajer"];

for (NSString *player in players) {
  NSLog(@"%@ is a champion!, player");
}
```

### Swift

```
for _ in 0...9 {
  print("Champions again ole ole!")
}
```

```
let players = ["Brown", "Forrest", "Ajer"]

for player in players {
  print("\(player) is a champion!")
}
```


## While loops

- Same besides the usual language specific parenthesis and semi colon differences


### Objective-C
```
NSInteger titles = 1;
NSInteger nineInRow = 9;

while(titles <= nineInRow) {
  NSLog(@"Champions again ole ole!");
  titles++;
}
```

```
var titles = 1
var nineInRow = 9

do {
  NSLog(@"Champions again ole ole!");
  titles++;
} while(titles <= nineInRow);
```

### Swift
```
var titles = 1
var nineInRow = 9

while titles <= nineInRow {
  print("Champions again ole ole!")
  titles++
}
```

```
var titles = 1
var nineInRow = 9

do {
  print("Champions again ole ole!")
  titles++
} while titles <= nineInRow
```

## switch statements

- `break` needed for Objective-C not Swift
- Use `fallthrough` to execute next case
- Objective-C only understands integers

### Objective-C
```
typedef NS_ENUM(NSUInteger, Team) {
    TeamUnknown = 0,
    GlasgowCeltic,
    ManchesterUnited,
    BorussiaDortmund
};

switch (team) {
    case GlasgowCeltic:
        NSLog(@"Hail Hail the Celts are here!");
        break;
    case ManchesterUnited:
        NSLog(@"Glory glory Man United!");
        break;
    case ManchesterUnited:
        NSLog(@"When you walk through a storm hold your head up high!");
        break;
    default:
        NSLog(@"No song found for team");
        break;
}

```

### Swift

```
enum Team: String {
  case glasgowCeltic
  case manchesterUnited
  case borussiaDortmund
}

switch(team) {
  case glasgowCeltic:
    print("Hail Hail the Celts are here!")
  case manchesterUnited:
    print("Glory glory Man United!")
  case borussiaDortmund:
    print(When you walk through a storm hold your head up high!)
  default:
    print("No song found for team")
}
```
