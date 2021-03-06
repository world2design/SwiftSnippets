# Swift Snippets
A collection of Swift snippets to be used in Xcode

## Usage

- swifttrycatch

```swift
do {
  try <#code#>
} catch <#errortype#> {
  <#code#>
} catch <#errortype#> {
  <#code#>
}
```

- swiftassociatedobject

```swift
private struct AssociatedKeys {
  static var <#name#> = "<#name#>"
}

var <#name#>: String? {
  get {
    return objc_getAssociatedObject(self, &AssociatedKeys.<#name#>) as? String
  }

  set {
    if let newValue = newValue {
      objc_setAssociatedObject(self, &AssociatedKeys.<#name#>, newValue as String?,
        .OBJC_ASSOCIATION_RETAIN_NONATOMIC
      )
    }
  }
}
```

- swiftavailable

```swift
@available(iOS 7, *)
```

- swiftcheckavailability

```swift
if #available(iOS 9, *) {
  <#code#>
} else {
  <#code>
}
```

- swiftcheckversion

```swift
#if swift(>=3.0)
    <#code#>
#elseif swift(>=2.2)
    <#code#>
#elseif swift(>=2.1)
    <#code#>
#endif
```

- swiftcheckplatform

```swift
#if os(iOS) || os(tvOS)
  <#code#>
#elseif os(watchOS)
  <#code#>
#elseif os(OSX)
  <#code#>
#endif
```

- swiftdispatchafter

```swift
let time = dispatch_time(DISPATCH_TIME_NOW, Int64(1 * Double(NSEC_PER_SEC)))
dispatch_after(time, dispatch_get_main_queue()) {
    <#code#>
}
```

- swiftdispatchasync

```swift
dispatch_async(dispatch_get_global_queue(QOS_CLASS_BACKGROUND, 0)) {
    <#code#>
}
```

- swiftdispatchonce

```swift
struct Static {
  static var token: dispatch_once_t = 0
}

dispatch_once(&Static.token) {
    <#code#>
}
```

- swiftinitcoder

```swift
public required init?(coder aDecoder: NSCoder) {
  fatalError("init(coder:) has not been implemented")
}
```

- swiftmark

```swift
// MARK: - <#section#>
```

- swiftsubscript

```swift
subscript(<#name#>: <#type#>) -> <#type#> {
  get {
    return <#value#>
  }
  set(newValue) {
      <#code#>
  }
}
```

- swifttypealias

```swift
typealias <#alias#> = <#existingtype#>
```

- swiftuitableviewdatasource
- swiftuicollectionviewdatasource
- swiftuipickerviewdatasource

## Installation

### Manual

Drag `codesnippet` files from `Snippets` into `/Library/Developer/Xcode/UserData/CodeSnippets`

### Automatic

Run this in your terminal

```
curl -fsSL https://raw.githubusercontent.com/hyperoslo/SwiftSnippets/master/install.sh | sh
```

## Author

Hyper Interaktiv AS, ios@hyper.no

## License

**SwiftSnippets** is available under the MIT license. See the LICENSE file for more info.
