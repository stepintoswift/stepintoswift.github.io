---
author: "Liam"
category: "Swift"
date: 2019-09-02 00:00:00
description: "Map Operator In action"
layout: post
permalink: map-operator-in-action
published: true
tags: [Map, Operator]
title: "How can I use the map operator in Swift?"
---

## Map Operator In Action

A real world example I created recently. A thing of beauty really...

In the example below we want to create a table view with a list of rows about say, a Football Player. A player can play at different clubs so in this example we want to show the club and the history at each club.

If you come to Swift from another language, you may write something like the below:

```
private func playerRowData(for players: [Player]) -> [PlayerRow.Data] {
        var playersRowData = [PlayerRow.Data]()

        for player in players {
            let history = "\(player.from) - \(player.to)"
            playersRowData.append(PlayerRow.Data(club: player.club, history: history))
        }

        return playersRowData
    }
```

This would be called at the call site as:

```
let playerRowData = playerRowData(for: players)
```

This is perfectly fine, however, instead of all the logic above, we can MAP IT! We remove the first block of code and replace the call site with:

```
let playerRowData = playerRowData.map { PlayersRow.Data(club: $0.club, history: "\($0.from) - \($0.to)") }
```

If we are using this logic in multiple places, we can even make the map a function as an extension on `Collection`:

```
extension Collection where Iterator.Element == Player {
	func mapToPlayersRowData() -> [PlayersRow.Data] {
        return map { PlayersRow.Data(club: $0.club, history: "\($0.from) - \($0.to)") }
    }
}
```

The call site is now:

```
let playerRowData = players.mapToPlayerRowData
```

Beautiful :chef-ok:
