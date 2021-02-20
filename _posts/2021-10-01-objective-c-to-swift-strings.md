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
