### Y-OS (OpenWrt Based) with Lean's Package

Y-os is based on OpenWrt. OpenWrt Project is a Linux operating system targeting embedded devices.   
Y-os基于OpenWrt，是一个适用于嵌入式设备的操作系统。

All releases and source codes are tested and works stability.  
所有的release和代码已经经过测试并可以使用

## Development

To build your own firmware you need a GNU/Linux, BSD or MacOSX system (case
sensitive filesystem required). Cygwin is unsupported because of the lack of a
case sensitive file system.  
为了能成功编译固件，您需要一个GNU/Linux/BSD或Mac OS X（需要Case Sensitive filesystem）系统。
Cygwin由于缺少包的支持，所以无法支持。

### Requirements

You need the following tools to compile OpenWrt, the package names vary between
distributions. A complete list with distribution specific packages is found in
the [Build System Setup](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem)
documentation.  
编译本固件至少需要以下包的支持：

```
gcc binutils bzip2 flex python3 perl make find grep diff unzip gawk getopt
subversion libz-dev libc-dev rsync
```

### Quickstart

Notice: This compile cannot be launched on root user!  
请注意：本编译不可在root用户下进行！

1. Run `./scripts/feeds update -a` to obtain all the latest package definitions
   defined in feeds.conf / feeds.conf.default  
   运行`./scripts/feeds update -a`以获取所有最新的包

2. Run `./scripts/feeds install -a` to install symlinks for all obtained
   packages into package/feeds/  
   运行`./scripts/feeds install -a`以安装前一步获取的包

3. Run `make menuconfig` to select your preferred configuration for the
   toolchain, target system & firmware packages.  
   运行`make menuconfig`以定制您的编译

4. Run `make -j8 download && make -j1 V=s` to build your firmware. This will download all sources, build the
   cross-compile toolchain and then cross-compile the GNU/Linux kernel & all chosen
   applications for your target system.  
   运行`make -j8 download && make -j1 V=s`以开始编译

### Special Thanks  
- [Lean's OpenWrt source](https://github.com/coolsnowwolf/lede)
- OpenWrt Contributers

## License  
[OpenWrt](http://www.openwrt.org/) and Y-OS is licensed under GPL-2.0
  
Sunshine!
