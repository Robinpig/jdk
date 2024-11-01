## Compile


## Debug

### Clion

`make compile-commands` 生成compile_commands.json文件

该文件会生成在macosx-aarch64-server-slowdebug目录下
打开CLion,操作路径： File > Open > compile_commands.json文件,选择Open as Project

之后CLion会做扫描和index,但是这时候还看不到源码相关的文件和目录,因为此时根目录是${openjdk源码目录}/build/macosx-x86_64-server-slowdebug, 需要更改项目根目录.

操作路径：Tools -> Compilation Database -> Change Project Root,选中OpenJDK的源码根目录,CLion再次扫描文件和建立index,结束后就可以看到源码了,且不会提示无法找到头文件

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
