# DD-WRT Firmwares for TP-LINK WR1043ND V1 after r33375 (09/19/17)

![GitHub release (latest by date)](https://img.shields.io/github/v/release/edgardmessias/dd-wrt-wr1043ndv1)
![GitHub All Releases](https://img.shields.io/github/downloads/edgardmessias/dd-wrt-wr1043ndv1/total)
![release](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/workflows/release/badge.svg)
![check-new-release](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/workflows/check-new-release/badge.svg)

Builds before [r33375](https://svn.dd-wrt.com/changeset/33375) (09/19/17) used "DD-WRT" as the string at the start of the firmware, and since that build they're all using "TP-LINK Technologies". Mtd partition code was looking for the wrong string to detect the bootloader size and upgrade via the web interface is not possible.

The objective of this repository is change back to "DD-WRT" in string header of the firmware when the ticket [6266](https://svn.dd-wrt.com/ticket/6266) is not solved. The solution is based on [this post](https://forum.dd-wrt.com/phpBB2/viewtopic.php?p=1124664#1124664).

Alternatively, a version for installation with [TFTP](https://community.tp-link.com/en/home/forum/topic/81462) is also generated (wr1043nv1_tp_recovery.bin)

Latest DD-WRT firmwares for WR1043ND V1 ![GitHub release (latest by date)](https://img.shields.io/github/v/release/edgardmessias/dd-wrt-wr1043ndv1) ![GitHub Releases](https://img.shields.io/github/downloads/edgardmessias/dd-wrt-wr1043ndv1/latest/total)

- [factory-to-ddwrt.bin](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/releases/latest/download/factory-to-ddwrt.bin): from TP-LINK to DD-WRT
- [tl-wr1043nd-webflash.bin](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/releases/latest/download/tl-wr1043nd-webflash.bin): DD-WRT upgrade
- [wr1043nv1_tp_recovery.bin](https://github.com/edgardmessias/dd-wrt-wr1043ndv1/releases/latest/download/wr1043nv1_tp_recovery.bin): TTFT Recovery

Links:

- https://svn.dd-wrt.com/ticket/6266
- https://svn.dd-wrt.com//changeset/33405/
- https://forum.dd-wrt.com/phpBB2/viewtopic.php?t=311642
- https://community.tp-link.com/en/home/forum/topic/81462
- https://forum.dd-wrt.com/phpBB2/viewtopic.php?p=1124664#1124664
