---
author: "Liam"
date: 2020-01-18 00:00:00
description: "Delegates to the Rescue"
layout: post
permalink: delegate-example
published: true
tags: [delegate, RxDataSources, SnapKit]
title: "How can delegates can solve TableView issues?"
---

# Real life delegate walkthrough

## Background

I recently ran into the following problem. I’ll talk through the first approach taken, followed by a better solution.

So the problem arose where I needed to update the height of a cell within a table view after an asynchronous image had finished loading from the server. 

Adding the code to update the cell produced unexpected output. The fix was in simply to wrap this update of the cell within a `tableView.beginUpdates()` and `tableView.endUpdates()`.

If you’ve architected your code in a way that the cell is in the same file as the table view, you’re done... But if you’ve separated your concerns, you'll find you'll have something like a xxxTableViewCell.swift and xxxViewController.swift.

This example uses the `RxDataSources` and `SnapKit` cocoapod that I will talk about in another article but the concept is the same no matter what you’re using.

> Check out my article on [Adding SnapKit]({% post_url 2019-09-23-adding-snapkit %}) to your project.

The ViewController defines a table view:

    private let tableView = UITableView()
    

Then within `viewDidLoad` we configure the table view with various types of cells:

```
override func viewDidLoad() {
        super.viewDidLoad()

        ...

        tableView.rowHeight = UITableView.automaticDimension
        tableView.register(cellClass: demoTableViewCell.self)

        view.addSubview(tableView)

        // layout the tableview with SnapKit for example
        ...

        setupTableViewDataSource()
    }
```

Within `setupTableViewDataSources()` depending on the cell we want :

```
private func setupTableViewDataSource() {
        let configCell: TableViewSectionedDataSource<DemoLayoutSection>.ConfigureCell = { [weak self] (_, tableView: UITableView, indexPath: IndexPath, item: DemoLayoutSection.Row) in
            switch item {
            case let .demoType(data):
                let cell = tableView.dequeueReusableCell(cellClass: DemoTableViewCell.self, for: indexPath)
                cell.configure(data: data)
                return cell
            }
        }
        
        ...
    }
```

Within the DemoTableViewCell we layout the cell. I’ve omitted this code but at the point where the image comes back from the server we have something like this:

```
...

let imageDownloadedHandler  = { [unowned self] (successfulCount: Int) in
            guard successfulCount == 1 else { return }

            self.imageControl.snp.updateConstraints { $0.height.equalTo(size.height) }
        }

...
```

## The Problem:

At this stage of the lifecycle the view has already been laid out, so updating the constraints won’t have any effect. 

Carrying out the `tableView.beginUpdates` and `tableView.endUpdates` would be great only we don’t have access to the tableView within our child.

What we could do is create a `weak var` on our child to hold the `table view` and then pass the table view in as a reference and we would have access to it like so:

### Child TableViewCell:

```
weak var tableView: UITableView

...

	let imageDownloadedHandler  = { [unowned self] (successfulCount: Int) in
		guard successfulCount == 1 else { return }

		guard let tableView = tableView else { return }

		tableView.beginUpdates()
		self.heroImageControl.snp.updateConstraints { $0.height.equalTo(size.height) }
		tableView.endUpdates()
}
```

Parent ViewController:

```
	case let .demoType(data):
		let cell = tableView.dequeueReusableCell(cellClass: DemoTableViewCell.self, for: indexPath)
		cell.tableView = tableView
		cell.configure(data: data)
		return cell
	}
```

This works, however the child now knows about the parent and good SOLID programming practices would tell us that we should not allow this.

## The Solution

What we should do is us a delegate. We can, use the child to tell the parent it is doing various things and respond accordingly within the correct parent class.

### Step 1 - Create the delegate protocol:

```
public protocol DemoTableViewCellDelegate: NSObject {
    func willBeginCellUpdate(_ cell: UITableViewCell)
    func didEndCellUpdate(_ cell: UITableViewCell)
}
```

### Step 2 - Child says it can be a delegate:

```
weak var delegate: DemoTableViewCellDelegate?
```
### Step 3 - Parent conforms to delegate:

```
case let .demoCell(data):
	let cell = tableView.dequeueReusableCell(cellClass: DemoCell.self, for: indexPath)
	cell.delegate = self
	cell.configure(data: data)
	return cell

extension ViewController: DemoTableViewCellDelegate {
    func willBeginCellUpdate(_ cell: UITableViewCell) {
        tableView.beginUpdates()
    }
    func didEndCellUpdate(_ cell: UITableViewCell) {
        tableView.endUpdates()
    }
}
```

### Step 4 - Child tells parent its state 

```
let imageDownloadedHandler  = { [unowned self] (successfulCount: Int) in
	guard successfulCount == 1 else { return }

	self.delegate?.willBeginCellUpdate(self)
	self.imageControl.snp.updateConstraints { $0.height.equalTo(size.height) }
	self.delegate?.didEndCellUpdate(self)
}
```

Now the child knows nothing about the parent > the parent is told by the child when it is finished / its state. 

Everything works as expected.

Now that you know how you can delegate in a real life example other than the out of the box Apple delegates, hopefully this will help with similar issues in future.