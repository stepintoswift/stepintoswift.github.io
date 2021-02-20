---
author: "Liam"
date: 2019-05-06 00:00:02
description: "Application Lifecycle"
layout: post
permalink: application-lifecycle
published: true
tags: [application lifecycle]
title: "What is the lifecycle of an iOS Application?"
---

## Application Lifecycle

Launch time:
- Application willFinishLaunchingWithOptions
- Application didFinishLaunchingWithOptions

Transitioning to the foreground:
- applicationDidBecomeActive

Transitioning to the background:
- applicationDidEnterBackground

Transitioning to the inactive state:
- applicationWillResignActive: Called when leaving the foreground
- applicationWillEnterForeground: Called when transitioning out of the background

Termination:
- applicationWillTerminate: Called only when the app is running. Not called if app is suspended

Related articles:
- [Application States]({% post_url 2019-05-06-app-states %})
