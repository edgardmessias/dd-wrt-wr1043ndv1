# DD-WRT Firmwares for TP-LINK WR1043ND V1 after r33375 (09/19/17)

![GitHub release (latest by date)](https://img.shields.io/github/v/release/edgardmessias/dd-wrt-wr1043ndv1)
![GitHub All Releases](https://img.shields.io/github/downloads/edgardmessias/dd-wrt-wr1043ndv1/total)
![release](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/workflows/release/badge.svg)
![check-new-release](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/workflows/check-new-release/badge.svg)

Builds before [r33375](https://svn.dd-wrt.com/changeset/33375) (09/19/17) used "DD-WRT" as the string at the start of the firmware, and since that build they're all using "TP-LINK Technologies". Mtd partition code was looking for the wrong string to detect the bootloader size and upgrade via the web interface is not possible. The problem is fixed in [r42928](https://svn.dd-wrt.com/changeset/42928).

The objective of this repository is generate a version for installation with [TFTP](https://community.tp-link.com/en/home/forum/topic/81462) is also generated (wr1043nv1_tp_recovery.bin)

## Latest DD-WRT firmwares for WR1043ND V1 ![GitHub release (latest by date)](https://img.shields.io/github/v/release/edgardmessias/dd-wrt-wr1043ndv1) ![GitHub Releases](https://img.shields.io/github/downloads/edgardmessias/dd-wrt-wr1043ndv1/latest/total)

- [wr1043nv1_tp_recovery.bin](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/releases/latest/download/wr1043nv1_tp_recovery.bin): TTFT Recovery
- [md5sum.txt](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/releases/latest/download/md5sum.txt): MD5 checksum file

## Troubleshooting

### Upgrade

If you installed a version after `r33375` and before `r42954`, first read this topic: https://forum.dd-wrt.com/phpBB2/viewtopic.php?t=311642

To upgrade from oficial DD-wrt release to this modified version, I recommend to use [TFTP method without serial console](https://openwrt.org/toh/tp-link/tl-wr1043nd#flashingrecovery_using_tftp_only_without_serial_console) with `wr1043nv1_tp_recovery.bin` file without losing your config.

As an alternative, you can back to TP-LINK firmware and upgrade with `factory-to-ddwrt.bin`.

### Unbrick/Debrick

First, you need check state of you `u-boot`, to do this, check the router leds:

#### LAN LEDs blinking -> `u-boot` is OK

Try unbrick with TFTP method:

https://openwrt.org/toh/tp-link/tl-wr1043nd#firmware_flashing

#### Only power LED is on -> `u-boot` problem

You need first rewrite `u-boot` using a JTAG method:

https://forum.openwrt.org/t/info-debricking-tplink-tl-wr1043nd-v-1-11-using-jtag/25682

Tip: Instead of run `flash write_image unlock ...`, append `erase` before of `unlock`, run `flash write_image erase unlock ...`

## Links:

- https://svn.dd-wrt.com/ticket/6266
- https://svn.dd-wrt.com//changeset/33405/
- https://forum.dd-wrt.com/phpBB2/viewtopic.php?t=311642
- https://community.tp-link.com/en/home/forum/topic/81462
- https://openwrt.org/toh/tp-link/tl-wr1043nd#flashingrecovery_using_tftp_only_without_serial_console
- https://forum.dd-wrt.com/phpBB2/viewtopic.php?p=1124664#1124664
- https://openwrt.org/docs/guide-user/hardware/debrick.ath79.using.jtag
- https://forum.openwrt.org/t/info-debricking-tplink-tl-wr1043nd-v-1-11-using-jtag/25682
