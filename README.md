# Simpo SDK

This is a dynamic framework which is distributed with closed sources.  
Latest version: 1.0.2

Can be installed either via Carthage or CocoaPod.

## Carthage
### Distribution via Carthage
Described [here](https://github.com/Carthage/Carthage#supporting-carthage-for-your-framework).

1. Prepare a binary framework:  
open a directory where `Simpo.xcworkspace` is located
2. Build and archive the framework _(TODO: a fat binary must be created!)_ :  
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
6. Edit the pushed tag directly on GitHub: Repo > Releases > Open the tag > Edit tag > set release title and attach a new version of the binary framework > Publish Release.

### SDK installation via Carthage

1. Install Carthage  
```bash
$ sudo gem install cocoapods
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
