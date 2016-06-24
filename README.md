# Viewer

[![Version](https://img.shields.io/cocoapods/v/Viewer.svg?style=flat)](https://cocoapods.org/pods/Viewer)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/bakkenbaeck/Viewer)
![platforms](https://img.shields.io/badge/platforms-iOS%20%7C%20OS%20X%20%7C%20watchOS%20%7C%20tvOS%20-lightgrey.svg)
[![License](https://img.shields.io/cocoapods/l/Viewer.svg?style=flat)](https://cocoapods.org/pods/DATAStack)

## Usage

From your UICollectionView:

```swift
override func collectionView(collectionView: UICollectionView, didSelectItemAtIndexPath indexPath: NSIndexPath) {
    guard let collectionView = self.collectionView else { return }

    let viewerController = ViewerController(initialIndexPath: indexPath, collectionView: collectionView)
    let headerView = HeaderView()
    headerView.viewDelegate = self
    self.viewerController?.headerView = headerView
    let footerView = FooterView()
    footerView.viewDelegate = self
    self.viewerController?.footerView = footerView
    viewerController.controllerDataSource = self
    self.presentViewController(viewerController, animated: false, completion: nil)
}

extension CollectionController: ViewerControllerDataSource {
    func viewerController(viewerController: ViewerController, itemAtIndexPath indexPath: NSIndexPath) -> ViewerItem {
        return self.photos[indexPath.row]
    }
}
```

## Installation

**Viewer** is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'Viewer'
```

**Viewer** is also available through [Carthage](https://github.com/Carthage/Carthage). To install
it, simply add the following line to your Cartfile:

```ruby
github "bakkenbaeck/Viewer"
```

## License

**Viewer** is available under the MIT license. See the LICENSE file for more info.

## Author

Bakken & Bæck, [@bakkenbaeck](https://twitter.com/bakkenbaeck)
