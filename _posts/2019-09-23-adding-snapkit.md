---
author: "Liam"
category: "Swift"
date: 2019-09-23 00:00:00
description: "Adding SnapKit to your project"
layout: post
permalink: adding-snapkit
published: false
tags: [Xcode, SnapKit]
title: "How do I add SnapKit to my Xcode project?"
---

## Setting up SnapKit

This is part 2 of our series on [setting up a new Xcode project with Coordinators, SnapKit and RxSwift](2019-09-02-xcode-coordinators-snapkit-rxswift-intro).

If you haven't already, make sure you have completed [Part 1: Installing Cocoapods](2019-09-09-installing-cocoapods).

In this article we will talk through adding [SnapKit](https://github.com/SnapKit/SnapKit) to your project so that we can use programmatic constraints instead of storyboards.

### Step 1

Rename `ViewController.swift` to `TestViewController.swift`

## Step 2

Replace the contents of `TestViewController` with:

```
import SnapKit

class TestViewController: UIViewController {

    lazy var box = UIView()

    override func viewDidLoad() {
        super.viewDidLoad()

        self.view.addSubview(box)
        box.backgroundColor = .green
        box.snp.makeConstraints { (make) -> Void in
            make.width.height.equalTo(50)
            make.center.equalTo(self.view)
        }
    }
}
```

### Step 3

Run the project and you should see a green box in the middle of the screen.

The green box comes compliments of [this PR](https://github.com/SnapKit/SnapKit/pull/61) within the [SnapKit](https://github.com/SnapKit/SnapKit) project.
