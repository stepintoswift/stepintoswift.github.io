---
author: "Liam"
category: "RxSwift"
date: 2019-08-03 00:00:01
description: "Map Operator - Extensions"
layout: post
permalink: rxswift-operator-map-extensions
published: true
tags: [Rx, ReactiveX, RxSwift, Operator, Map, Transforming]
title: "Using extensions with the RxSwift Map Operator"
---

## RxSwift: Extensions with Map Operator

Check out my [Map Operator post]({% post_url 2019-05-27-rxswift-operator-map %}) for an overview of the map operator.

A more complex example of the map operator could be mapping a list of results
to a row for a table view.

### Example 1: Stream of results
```
Observable.of("James Forrest", "Scott Brown", "Ryan Christie")
            .map { return ProofCell.Data(title: $0) }
            .toArray()
            .map { proofCellDataResponse -> [ProofRow] in
                return proofCellDataResponse.map({ proofCellData -> ProofRow in
                    return ProofRow.proof(data: proofCellData)
                })
            }
            .subscribe(onNext: { [weak self] sections in
                self?.rows.accept(sections)
            })
            .disposed(by: disposeBag)
```

A nicer way to do this, so we move the nested mapping logic out of the closure would
be to create an extension on the `ObserablveType` where our type is equal to the
type that we are expecting to receive:

```
extension ObservableType where E == [ProofCell.Data] {
    fileprivate func mapToRows() -> Observable<[ProofRow]> {
        return map { proofCellDataResponse -> [ProofRow] in
            return proofCellDataResponse.map({ proofCellData -> ProofRow in
                return ProofRow.proof(data: proofCellData)
            })
        }
    }
}
```

This makes our call site clean allowing us just to call `mapToRows`:

```
Observable.of("James Forrest", "Scott Brown", "Ryan Christie")
            .map { return ProofCell.Data(title: $0) }
            .toArray()
            .mapToRows()
            .subscribe(onNext: { [weak self] sections in
                self?.rows.accept(sections)
            })
            .disposed(by: disposeBag)
```

### Example 2: Array of results

Another example where say we received `just` an array of results could be:

```
Observable<[String]>.just(["James Forrest", "Scott Brown"])
            .map { stringArrayResponse -> [ProofRow] in
                stringArrayResponse.map({ stringItem -> ProofRow in
                    let data = ProofCell.Data(title: stringItem)
                    return ProofRow.proof(data: data)
                })
            }
            .subscribe(onNext: { [weak self] sections in
                self?.rows.accept(sections)
            })
            .disposed(by: disposeBag)
```

Again we can extract this mapping logic out into an extension:

```
extension ObservableType where E == [String] {
    fileprivate func mapToRows() -> Observable<[ProofRow]> {
        return map { proofCellDataResponse -> [ProofRow] in
            return proofCellDataResponse.map({ proofCellData -> ProofRow in
                let data = ProofCell.Data(title: proofCellData)
                return ProofRow.proof(data: data)
            })
        }
    }
}
```

Which leaves the call site clean once again:

```
Observable<[String]>.just(["James Forrest", "Scott Brown"])
            .mapToRows()
            .subscribe(onNext: { [weak self] sections in
                self?.rows.accept(sections)
            })
            .disposed(by: disposeBag)
```
