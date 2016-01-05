# ReuseCellConfigure

[![Version](https://img.shields.io/cocoapods/v/ReuseCellConfigure.svg?style=flat)](http://cocoapods.org/pods/ReuseCellConfigure)
[![License](https://img.shields.io/cocoapods/l/ReuseCellConfigure.svg?style=flat)](http://cocoapods.org/pods/ReuseCellConfigure)
[![Platform](https://img.shields.io/cocoapods/p/ReuseCellConfigure.svg?style=flat)](http://cocoapods.org/pods/ReuseCellConfigure)

## Usage

To run the example project, clone the repo, and run `pod install` from the Example directory first.

```swift
func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell {
    let cell: UITableViewCell?
    let alphabet = String(UnicodeScalar("A".unicodeScalars.first!.value + UInt32(indexPath.row)))
    switch indexPath.row % 2 {
        case 0:
            cell = tableView.dequeueReusableCellWithIdentifier("LeftIconTableViewCell", classForCell: LeftIconTableViewCell.self) {
                $0.alphabetLabel.text = alphabet
                $0.randomBackgoundColor()
            }
        case 1:
            cell = tableView.dequeueReusableCellWithIdentifier("RightIconTableViewCell", classForCell: RightIconTableViewCell.self) {
                $0.alphabetLabel.text = alphabet
            }
        default:
            cell = tableView.dequeueReusableCellWithIdentifier("UITableViewCell")
    }
    return cell!
}
```

## Requirements

## Installation

ReuseCellConfigure is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "ReuseCellConfigure"
```

## Author

Taiki Suzuki, s1180183@gmail.com

## License

ReuseCellConfigure is available under the MIT license. See the LICENSE file for more info.
