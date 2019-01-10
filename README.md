# Simpo SDK

This is a dynamic framework which is distributed with closed sources.  
Latest version: 1.0.5

Installation instructions:
- [Carthage](#carthage)
- [CocoaPods](#cocoapods)

### Carthage

1. Install Carthage  
```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install carthage
```
2. Create `Cartfile` in the project root dir with the content:  
`github "vvit/SimpoSDK"`  
_TODO: update repo path_  
3. Install the dependency:  
`carthage update --platform iOS`
4. Add `Simpo.framework` (located in `<project-root>/Carthage/Build/iOS`) to the `Linked Frameworks and Libraries`:  
![picture](https://github.com/vvit/SimpoSDK/blob/master/carthage1.png)
5. Add a `Run Script` build phase with this content:  
![picture](https://github.com/vvit/SimpoSDK/blob/master/carthage2.png)


## CocoaPods

1. Install CocoaPods  
```bash
$ sudo gem install cocoapods
```
2. If needed (first time) run: `pod init`
3. Install the dependency by adding `pod 'SimpoTest'` _(TODO: update name)_ into the `Podfile`  
Then run
```bash
$ pod update
```

So the `Podfile` looks like this:  
```bash
platform :ios, '9.3'

target 'CocoapodExample' do
  use_frameworks!
  pod 'SimpoTest'
end
````
