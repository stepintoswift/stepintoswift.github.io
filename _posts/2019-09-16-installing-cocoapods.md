---
author: "Liam"
category: "Swift"
date: 2019-09-16 00:00:00
description: "Setting up Cocoapods"
layout: post
permalink: installing-cocoapods
published: true
tags: [Xcode, Coordinators, SnapKit, RxSwift, Cocoapods]
title: "How do I set up a new Xcode workspace with Cocoapods?"
---

## Setting up a new project with Cocoapods

This is part 1 of our series on [setting up a new Xcode project with Coordinators, SnapKit and RxSwift]({% post_url 2019-09-09-xcode-coordinators-snapkit-rxswift-intro %}).

In this article we will create a Xcode Workspace via the use of [Cocoapods](https://cocoapods.org/){:target="_blank"}. So let's open terminal, navigate to your Xcode project and get started.

### Step 1: Install Cocoapods

```
sudo gem install cocoapods
```

### Step 2: Create a Podfile

```
pod init
```

### Step 3: Edit the Podfile (I'm using Atom here)

```
atom Podfile
```

### Step 4: Add the various base pods, Swiftlint and the post_install section

```
platform :ios, '11.0'
pod 'SwiftLint'

target 'StepIntoSwift' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for StepIntoSwift
  pod 'RxCocoa', '~> 5'
  pod 'RxDataSources', '~> 4.0'
  pod 'RxSwift', '~> 5'
  pod 'SnapKit', '~> 5.0.0'

  target 'StepIntoSwiftTests' do
    inherit! :search_paths
    # Pods for testing
  end

end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['SWIFT_VERSION'] = '5.0'
    end
  end
end

```

### Step 5: Install the pods listed in the Podfile:

```
pod install
```

Your terminal will output something like the below:

```
Analyzing dependencies
Downloading dependencies
Installing Differentiator (4.0.1)
Installing RxCocoa (5.0.0)
Installing RxDataSources (4.0.1)
Installing RxRelay (5.0.0)
Installing RxSwift (5.0.0)
Installing SnapKit (5.0.0)
Installing SwiftLint (0.34.0)
Generating Pods project
Integrating client project

[!] Please close any current Xcode sessions and use `ProjectName.xcworkspace` for this project from now on.
Sending stats
Pod installation complete! There are 5 dependencies from the Podfile and 7 total pods installed.
```

### Step 6: Open the Xcode "Workspace":

```
open ProjectName.xcworkspace
```

### Step 7: Run your project as normal
