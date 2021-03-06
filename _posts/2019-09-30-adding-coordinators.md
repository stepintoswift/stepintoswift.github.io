---
author: "Liam"
category: "Swift"
date: 2019-09-30 00:00:00
description: "Adding the Coordinator pattern"
layout: post
permalink: adding-coordinators
published: true
tags: [Xcode, Coordinators, Coordinator pattern]
title: "How do I use the Coordinator pattern?"
---

## Adding Coordinators

This is Part 3 of my series on [Setting up a new Xcode project with Coordinators, SnapKit and RxSwift]({% post_url 2019-09-09-xcode-coordinators-snapkit-rxswift-intro %}).

If you're just here for the Coordinators, feel free to read on. If you'd like the full project / workspace, please see the previous articles:

1. [Overview - Setting up a new Xcode project with Coordinators, SnapKit and RxSwift]({% post_url 2019-09-09-xcode-coordinators-snapkit-rxswift-intro %}).
2. [Installing Cocoapods]({% post_url 2019-09-16-installing-cocoapods %}).
3. [Adding SnapKit]({% post_url 2019-09-23-adding-snapkit %}).

### Why Coordinator's?

Navigation should not be the responsibility of the ViewController:

```
@IBAction func goToNextViewController(_ sender: UIButton) {
      performSegue(withIdentifier: "nextViewController", sender: self)
  }
```

Having segues in storyboards and using segues in view controllers's is very restrictive. We should always seek to separate our concerns and use the single responsibility principle.

The Coordinator pattern solves the problem an out of the box, "hello world" architecture introduces of tightly coupling our application flow.

The set up below is a one off and afterwards we will be able to navigate anywhere in an app, from anywhere, very easily. We will use RxSwift in a later article to do this in a really cool way.

Let's get started...

NB: This will work with `Xcode 10.3` or below.

### Step 1:

Create a `Coordinator.swift` protocol:

```
import UIKit

protocol Coordinator {
    var childCoordinators: [Coordinator] { get set }
    var navigationController: UINavigationController { get set }

    func start()
}
```

### Step 2:

Create a `ApplicationFlowCoordinator.swift` concrete class:

```
import RxSwift

class ApplicationFlowCoordinator: Coordinator {

    // MARK: - Private properties -

    private let disposeBag: DisposeBag = DisposeBag()
    private var window: UIWindow

    // MARK: - Internal properties -

    var childCoordinators = [Coordinator]()
    var navigationController: UINavigationController

    // MARK: - Initialization -

    init(navigationController: UINavigationController, window: UIWindow) {
        self.window = window
        self.navigationController = navigationController
    }

    // MARK: - Internal methods -

    func start() {
        showEntryViewController()
    }

    // MARK: - Private methods -

    private func showEntryViewController() {
        let viewController = ViewController()

        navigationController.viewControllers = [viewController]
        window.rootViewController = navigationController
    }

    private func showViewController(_ viewController: UIViewController) {
        navigationController.pushViewController(viewController, animated: true)
    }
}
```

### Step 3

Update your `AppDelegate.swift` with the `didFinishLaunchingWithOptions` function and the internal properties:

```
import UIKit

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    var applicationFlowCoordinator: ApplicationFlowCoordinator!
    var window: UIWindow?

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {

        let navigationController = UINavigationController()

        let window = UIWindow(frame: UIScreen.main.bounds)
        window.backgroundColor = .white

        applicationFlowCoordinator = ApplicationFlowCoordinator(navigationController: navigationController, window: window)
        applicationFlowCoordinator.start()

        window.makeKeyAndVisible()
        self.window = window

        return true
    }

    func applicationWillResignActive(_ application: UIApplication) { }

    func applicationDidEnterBackground(_ application: UIApplication) { }

    func applicationWillEnterForeground(_ application: UIApplication) { }

    func applicationDidBecomeActive(_ application: UIApplication) { }

    func applicationWillTerminate(_ application: UIApplication) { }
}
```

## Step 4

Delete `Main.storyboard`

## Step 5

Go to project file and delete `Main Interface` which is currently `Main`. The `AppDelegate` will control this now.

## DONE!

Run and things should be as they where, only now, we’re using Coordinators to control the application flow.
