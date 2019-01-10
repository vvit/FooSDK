# Simpo SDK

This is a dynamic framework which is distributed with closed sources.  
Latest version: 1.0.5

Can be installed using these dependency managers:
- [Carthage](#carthage)
- [CocoaPods](#cocoapods)

## Carthage
### Distribution via Carthage
Described [here](https://github.com/Carthage/Carthage#supporting-carthage-for-your-framework).

1. Prepare a binary framework:  
open a directory where `Simpo.xcworkspace` is located
2. Build and archive the fat dynamic framework:  
```bash
$ carthage build --archive
```
or 
```bash
$ carthage build --no-skip-current
$ carthage archive Simpo
```
 
3. Do some changes in a public GitHub repo. Can be installation instructions or `What's New` section update in `README.md`.
4. Create and push a new commit with the changes.
5. Create and push a new tag:  
```bash
$ git tag -a v1.0.0 -m "New version info"
$ git push --tags
```
6. Edit the pushed tag directly on GitHub: Repo > Releases > Open the tag > Edit tag > set release title and attach a new version of the zipped binary framework (located at `<project-root>/Simpo.framework.zip`) > Publish Release.

### SDK installation via Carthage

1. Install Carthage  
```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install carthage
```
2. Create `Cartfile` in the project root dir with the content:  
`github "vvit/SimpoSDK" ~> 1.0` or `github "vvit/SimpoSDK" >= 1.0.1`
3. Install the dependency:  
`carthage update --platform iOS` or `carthage bootstrap`
4. Add `Simpo.framework` (located in `<project-root>/Carthage/Build/iOS`) to the `Linked Frameworks and Libraries`:  
![picture](https://github.com/vvit/SimpoSDK/blob/master/carthage1.png)
5. Add a `Run Script` build phase with this content:  
![picture](https://github.com/vvit/SimpoSDK/blob/master/carthage2.png)


## CocoaPods
### Distribution via CocoaPods
1. Prepare a binary framework: open `Simpo.xcworkspace`
2. Select `Simpo` target and `Generic iOS Device` on top panel
3. Run `Product > Archive` 
4. Wait until the Finder opens the folder with the zipped framework (root project dir). It takes a while so need to wait.
5. The zipped file can be used as an attachment in the new GitHub Release.
6. Update `SimpoTest.podspec` and set new version and the new framework URL of the github release (in `s.version` and `s.source`)
7. (If needed) check the edited spec file: `pod spec lint`
8. (If needed) register the cocoa pod trunk: `pod trunk register yourname@yourcompany.com 'Your Name'`
9. Publish the pod: `pod trunk push SimpoTest.podspec` (takes a while since the binary will be checked).

### SDK installation via CocoaPods

1. Install CocoaPods  
```bash
$ sudo gem install cocoapods
```
2. Install the dependency by adding this `pod 'SimpoSDK'` into the `Podfile`  
Then run
```bash
$ pod update
```
