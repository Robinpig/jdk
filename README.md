


> Ref [building.md](https://github.com/openjdk/jdk/blob/master/doc/building.md)

支持编译的平台:
[Supported Build Platforms](https://wiki.openjdk.org/display/Build/Supported+Build+Platforms)

Mac aarch64从jdk11开始支持




1. Get the complete source code:<br/>
   `git clone https://git.openjdk.org/jdk/`
2. Run configure:<br/>
   `bash configure --with-debug-level=slowdebug --with-jvm-variants=server`
   当WSL下 需要增加`--build=x86_64-unknown-linux-gnu --host=x86_64-unknown-linux-gnu`
    若配置jdk麻烦 可直接使用`--with-boot-jdk=<jdk path>`
3. Run make:<br/>
   `make images`



[segmentation fault in the jvm](https://mail.openjdk.org/pipermail/jdk7-dev/2011-March/001983.html)


## Compile

Mac

make sure you have installed Xcode
```shell
brew install ccache freetype autoconf
```

## Debug

### Clion

`make compile-commands` 生成compile_commands.json文件

该文件会生成在macosx-aarch64-server-slowdebug目录下
打开CLion,操作路径： File > Open > compile_commands.json文件,选择Open as Project

之后CLion会做扫描和index,但是这时候还看不到源码相关的文件和目录,因为此时根目录是${openjdk源码目录}/build/macosx-x86_64-server-slowdebug, 需要更改项目根目录.

操作路径：Tools -> Compilation Database -> Change Project Root,选中OpenJDK的源码根目录,CLion再次扫描文件和建立index,结束后就可以看到源码了,且不会提示无法找到头文件

Settings -> build, Execution, Deployment -> Custom Build Targets

create External Tools

- Program: make
- Arguments: CONF=xxxx
- Working directory: root directory


create Toolchain



edit Run/Debug Configurations

create Custom Build Application

- Target: toolchain
- Executable: java
- Program arguments: -version


如果进入 LLDB 断点，可以在 LLDB 命令行中输入 pro hand -p true -s false SIGILL SIGSEGV SIGBUS



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







