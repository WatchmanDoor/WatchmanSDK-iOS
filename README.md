# WatchmanSDK for iOS
WatchmanSDK for iOS helps developers to integrate our products in their own systems. Developed by a core team of engineers at Watchman Door, these components enable a reliable development workflow.

## Requirements
* XCode 10 or higher
* Swift 5 or higher
* Minimum iOS deployment target of 11.0 or higher

### Requiered CocoaPods

```
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
    1. WatchmanSDK
    1. WDCommon
    1. WDNetwork
    1. WDConnectivity
1. Go to your project `Target > General > Embedded Binaries` and add them.
> Make sure that the recently frameworks appears into Linked Frameworks and Libraries

### Importing
```swift
import WatchmanSDK
```
