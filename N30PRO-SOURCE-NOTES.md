# Netcore N30 Pro build source snapshot

This branch records the source tree used to build the verified full-featured
Netcore N30 Pro firmware.

## Base and device support

- ImmortalWrt base commit: `46a15c769f3f74dfbfcbe33b25ca7a41a140493b`
- Netcore N30 Pro device definition follows PR 431 head:
  `265b0b51fd9337e65fb79e87c89d1a17b02e008e`
- The N30 Pro defaults include:
  - LAN address `192.168.6.1`
  - root password `password`
  - 2.4 GHz SSID `ImmortalWrt`
  - 5 GHz SSID `ImmortalWrt-5G`
  - wireless country `CN`
  - 5 GHz `HE160`
- The accidental `02_network.orig` backup is not included. The generated
  network layout is four LAN ports plus one WAN port.
- The FIP partition remains read-only and is not written by sysupgrade.

## Vendored package snapshots

The build directory originally contained these packages as nested Git
checkouts. They are committed here as ordinary source files so this branch
also preserves their local build-time modifications.

- OpenClash upstream commit:
  `c3a33c1d3407956fdf8f0e0b7c1a4c52e6ad9593`
- PassWall upstream commit:
  `f91f3e5f22f514edb83216fa1deeab988c6e0cd5`
  - Includes the local LuCI/default-setting changes present in the build tree.
- PassWall packages upstream commit:
  `50de2d79993447258b1bc15a667a6fb1cd6e7222`
  - Includes the local `geoview` and `sing-box` Makefile changes present in
    the build tree.

## Reproducing the configuration

```sh
cp configs/netcore-n30-pro-full.config .config
make defconfig
make -j$(nproc)
```

The saved configuration contains the full-featured package selection used by
the successful `n60-openwrt-build` virtual-machine build.
