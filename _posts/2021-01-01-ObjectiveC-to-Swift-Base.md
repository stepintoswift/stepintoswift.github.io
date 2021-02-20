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

## Overview

You thought that time was over.
Those square brackets and pointers.
It's safe here in Swift land, you'll not have to worry about that again they thought
Until... you're landed with a 10 year old Objective-C app to work with, add features to and convert to Swift.

In order to reacquaint myself with Objective-C and help, what seems to be a lot of engineers who haven't touch it before, I'll be putting together a series of articles to help you get over those initial hurdles and back into square brackets land.

================================================================================


Ideas:
- [x] Variables and Constants
- [x] Arrays
- [x] Dictionaries
- [x] Enums
- [x] String Interpolation
- [x] Control flow (if, for, switch, ...)
- [x] Functions
- [x] Classes
- [x] Structs
- [x] Types
- [ ] Tuples
- [x] Semi-Colons
- [ ] Optionals
- [ ] Blocks and Closures
- [x] Header files
- [x] Square brackets

================================================================================

# File Types

- Objective-C
  - `.h` : Header file (Like an interface)
  - `.m` : Implementation file (Implement the interface and additional private methods)

- Swift
  - `.swift`

================================================================================

# Semicolons

- Semicolons at the end of lines are optional.
- Useful if you're putting multiple lines on the same line.
- Used in traditional for loops

================================================================================

# Types

- Swift types are all objects
- Swift types are mutable

| Objective-C | Swift |
|---|---|
| `NSInteger`         | `Int` |
| `NSUInteger`        | `UInt` |
| `char`              | `Int8` |
| `char`              | `Character` |
| `unsigned char`     | `UInt8` |
| `short`             | `Int16` |
| `unsigned short`    | `UInt16` |
| `int`               | `Int32` and `UInt32` |
| `long`              | `Int64` |
| `float`             | `Float` |
| `double`            | `Double` |
| `BOOL`              | `Bool` |
| `id`                | `AnyObject` |
| `Class`             | N/A |
| `IMP`               | N/A |
| SEL                 | `Selector` |
| `void`              | `Void` |

================================================================================

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

================================================================================

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

================================================================================

# Enum

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

================================================================================

# Strings

## Objective-C

```
NSString *neverWonTheLeague = @"Never won the league: ";
NSString *whoHasNeverWonTheLeague = [neverWonTheLeague stringByAppendingString: @"Slippy G!"];
```

String Interpolation

```
NSString *player = @"Slippy G";
NSString *whoHasNeverWonTheLeague = [NSString stringWithFormat: @"Never won the league: %@", slippyG];
```


## Swift

```
let neverWonTheLeague = "Never won the league: "
let whoHasNeverWonTheLeague = neverWonTheLeague + "Slippy G!"
```

String Interpolation

```
let player = "Slippy G"
let hasNeverWonTheLeague = "Never won the league \(player)"
```

================================================================================

# Print and NSLog

To print to the console:

| Objective-C | Swift |
|---|---|
| `NSLog(@"Hail Hail!");` | `print("Hail Hail!")` |


================================================================================

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

================================================================================

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



================================================================================

# Blocks and Closures

================================================================================

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

================================================================================

# Structs

## Objective-C

- Objective-C has no concept of structs.
- Structs are widely used (and preferred over classes) in Swift.

## Swift

```
struct Player {
  let name: String
}
```

================================================================================

# Memory management

## Objective-C

```
```

## Swift

```
```

================================================================================

# Protocols

## Objective-C

```
```

## Swift

```
```

================================================================================
