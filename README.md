# WatchmanSDK for iOS
WatchmanSDK for iOS helps developers to integrate our products into their own systems. Developed by a core team of engineers at Watchman Door, these components enable a reliable development workflow.

## Requirements
* XCode 11 or higher
* Swift 5.1 or higher
* Minimum iOS deployment target of 11.0 or higher

### Requiered CocoaPods

```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '11.0'
use_frameworks!

workspace 'Example.xcworkspace' 

target 'Example' do
    
    project 'Example.xcodeproj'
    pod 'RxSwift', '~> 5.0'
    pod 'RxCocoa', '~> 5.0'
    pod 'Swinject', '~> 2.0'
    pod 'SwinjectAutoregistration', '~> 2.0'
    
end
```

## Installation
To be able to use WatchmanSDK in your iOS project follow this steps:
1. Download the content of this repository and copy into your project directory:
    * WatchmanSDK
    * WDCommon
    * WDNetwork
    * WDConnectivity
1. Go to your project `Target > General > Embedded Binaries` and add them.
> Make sure that the recently added frameworks appear into `Linked Frameworks and Libraries`

### Importing
```swift
import WatchmanSDK
```

## Usage
### Typical use: Instantiate the desired WDManager and implement their delegates
```swift
import WatchmanSDK

class ViewController: UIViewController {

    var loginManager: WDLoginManager? = nil
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        loginManager = WDLoginManager(delegate: self)
        loginManager?.doLogin(withEmail: "mail@mail.com", andPassword: "Password")
    }
    
    ...

}

extension ViewController: WDLoginDelegate {

    func WDLoginResponse(loginOK: Bool, error: Int?) {
        if loginOK {
            addLog(message:"LOGIN OK!")
        } else {
            addLog(message:"LOGIN KO!: \(error ?? 500)")
        }
    }

    func WDUserClosedSession() {
        addLog(message:"THE USER HAS LOGGED OUT!")
    }
}
```
