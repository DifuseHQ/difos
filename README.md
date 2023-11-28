<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://i.imgur.com/queGRtS.png">
  <source media="(prefers-color-scheme: light)" srcset="https://i.imgur.com/pR97tbF.png">
  <img alt="DifOS - Logo" src="https://i.imgur.com/pR97tbF.png">
</picture>

[![Build Status](https://ci.difuse.io/buildStatus/icon?job=DifOS)](https://ci.difuse.io/job/DifOS/) 

DifOS is part of the Difuse Project, firmware that is based on OpenWrt and is available for use on DMSBG devices.

## Download

Built firmware is available for download [here](https://gin.difuse.io/downloads).

## Development

To build your own firmware you need a GNU/Linux, BSD or MacOSX system (case
sensitive filesystem required). Cygwin is unsupported because of the lack of a
case sensitive file system.

### Requirements

[Build System Setup](https://openwrt.org/docs/guide-developer/build-system/install-buildsystem) is pretty much identical to that of OpenWRT. Below given are the common packages required to build the firmware.

```
binutils bzip2 diff find flex gawk gcc-6+ getopt grep install libc-dev libz-dev
make4.1+ perl python3.7+ rsync subversion unzip which
```

### Quickstart

1. Run `./scripts/feeds update -a` to obtain all the latest package definitions
   defined in feeds.conf / feeds.conf.default

2. Run `./scripts/feeds install -a` to install symlinks for all obtained
   packages into package/feeds/

3. Run `mv dmsbg100.config .config && make defconfig` to use the default
   configuration for the DMSBG100 device.

4. Run `make` to build your firmware. This will download all sources, build the
   cross-compile toolchain and then cross-compile the GNU/Linux kernel & all chosen
   applications for your target system.

### Related Repositories

The main repository uses multiple sub-repositories to manage packages of
different categories. All packages are installed via the OpenWrt package
manager called `opkg`. If you're looking to develop the web interface or port
packages to OpenWrt, please find the fitting repository below.

* [LuCI Web Interface](https://github.com/DifuseHQ/luci): Modern and modular
  interface to control the device via a web browser.

* [DifOS Packages](https://github.com/DifuseHQ/packages): Community repository
  of ported packages.

* [DifOS Routing](https://github.com/DifuseHQ/routing): Packages specifically
  focused on routing.

* [DifOS Telephony](https://github.com/DifuseHQ/telephony): Packages specifically
  focused on telephony.

### Support Community

* [Forum](https://forum.difuse.io): For usage, projects, discussions and hardware advice.
* [Support Chat](https://discord.gg/u6RupFDMp9): Discord server for support and general discussion.

## License

DifOS is licensed under GPL-2.0
