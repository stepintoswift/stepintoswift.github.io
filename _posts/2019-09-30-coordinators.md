---
author: "Liam"
category: "Swift"
date: 2019-09-30 00:00:00
description: "Adding the Coordinator pattern"
layout: post
permalink: adding-coordinators
published: false
tags: [Xcode, Coordinators, Coordinator pattern]
title: "How do I use the Coordinator pattern?"
---

## Adding Coordinators

This is Part 3 of my series on [Setting up a new Xcode project with Coordinators, SnapKit and RxSwift.]()

If you're just here for the Coordinators, feel free to read on. If you'd like the full project / workspace, please see the previous articles:

1. [Overview]()
2. [Installing Cocoapods]()
3. [Adding SnapKit]()

### Why Coordinator's

Navigation should not be the responsibility of the ViewController:

```
@IBAction func goToNextViewController(_ sender: UIButton) {
      performSegue(withIdentifier: "nextViewController", sender: self)
  }
```

Having segues in storyboards and using segues in ViewController's is very restrictive. We should always seek to separate our concerns and use the single responsibility principle.

The Coordinator pattern solves the problem an out of the box, hello world architecture introduces of tightly coupling our application flow.

The set up below is a one off thing and afterwards we will be able to navigate anywhere in an app very easily. We will use RxSwift in a later article to do this in a really cool way.

Let's get started...

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
        showTestViewController()
    }

    // MARK: - Private methods -

    private func showTestViewController() {
        let viewController = TestViewController()

        navigationController.viewControllers = [viewController]
        window.rootViewController = navigationController
    }

    private func showViewController(_ viewController: UIViewController) {
        navigationController.pushViewController(viewController, animated: true)
    }
}
```

### Step 3

Replace `AppDelegate.swift` with:

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

Go to project file and delete `Main Interface`. The `AppDelegate` will control this now.

## DONE!

Run and things should be as they where, only now, we’re using Coordinators to control the application flow.
