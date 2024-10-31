## Issues


### Mac

编译环境: m1 mac jdk21

报错如下

```
configure: WARNING: Ignoring the located xcodebuild tool /usr/bin/xcodebuild due to an error: xcode-select: error: tool 'xcodebuild' requires Xcode, but active developer directory '/Library/Developer/CommandLineTools' is a command line tools instance
checking if metal can be run using xcrun... no
configure: error: XCode tool 'metal' neither found in path nor with xcrun
configure exiting with result code 1
```

执行

```shell
sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
```
