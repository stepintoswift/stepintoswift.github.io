---
author: "Liam"
date: 2019-05-07 00:00:00
description: "What is the lifecycle of an iOS Application?"
layout: post
permalink: application-lifecycle
published: true
tags: [application lifecycle]
title: "Application Lifecycle"
---

## Application Lifecycle

Launch time:
- Application willFinishLaunchingWithOptions
- Application didFinishLaunchingWithOptions

Transitioning to the foreground:
- applciationDidBecomeActive

Transitioning tot he background:
- applicationDidEnterBackground

Transitioning to the inactive state:
- applicationWillResignActive: Called when leaving the foreground
- applciationWillEnterForeground: Called when transitioning out of the background

Termination:
- applciaitonWillTerminate: Called only when the app is running. Not called if app is suspended

Related articles:
- [Application States]({% post_url 2019-05-06-app-states %})
