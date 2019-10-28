---
author: "Liam"
category: "Swift"
date: 2019-09-09 00:00:00
description: "Xcode Project with Coordinators, SnapKit and RxSwift"
layout: post
permalink: xcode-coordinators-snapkit-rxswift-intro
published: true
tags: [Xcode, Coordinators, SnapKit, RxSwift, Cocoapods]
title: "How do I set up a project with Coordinators, SnapKit and RxSwift?"
---

## Setting up a new Xcode project with Coordinators, SnapKit and RxSwift

When you manage to get through your first few "Hello World" projects or working on projects that tightly couple your storyboards, you'll find that the out of the box Apple way of creating projects has its drawbacks and limitations. Some projects are fine to keep going this route but when you're ready to move to the next level, in the next series of posts I'll show you how I configure my projects.

- I use the Coordinator Pattern as thought up by [Sorush Khanlou](http://khanlou.com/){:target="_blank"} and nicely documented by [Paul Hudson](https://www.hackingwithswift.com/){:target="_blank"}
- I no longer use storyboards and use a framework called SnapKit which I have also contributed to.
- Finally, as you can see from my older posts, I use RxSwift.
- These are all set up as dependencies via Cocoapods.

I will take you through the set up of each of these in the following posts:

1. [Setting up a new project to use Cocoapods]({% post_url 2019-09-16-installing-cocoapods %}).
2. [Adding SnapKit]({% post_url 2019-09-23-adding-snapkit %}).
3. [Setup your project to use the Coordinator Pattern]({% post_url 2019-09-30-adding-coordinators %})
4. Simple navigation with RxSwift (Coming soon)
