## Minimal, XFCE and LXQt Remixes

The major differences between Fedora arm releases as compared to Fedbery releases are:
- The use of our own custom [kernels](https://github.com/fedberry/kernel) (based on Raspberry Pi foundation's bcm2709 kernel port) which provides equivalent hardware support as Raspbian / Pixel.
- The use of Raspberry Pi foundation's own bootloader (ie. we don't use uboot).
- Inclusion of additional software such as:
  * Raspberry Pi VideoCore GPU [libraries & utilities](https://github.com/fedberry/raspberrypi-vc)
  * [fedberry-config](https://github.com/fedberry/fedberry-config)
  * [chromium](https://github.com/fedberry/chromium)
  * [omxplayer](https://github.com/fedberry/omxplayer)
- The use of swap files in lieu of swap partitions.
- Having /tmp on tmpfs is enabled but size limited to 100M.
- The root partition is automatically set to resize on first boot.
- To facilitate optional headless booting, a default root password (fedberry) is set in the 'minimal' release.

## Barebone Remix

This release is for ADVANCED users only, as it differs significantly from our other remixes. As the name suggests, it is a small 'bare bones' remix with various optimisations specifically tailored towards Rapsberry^ Pi 2/3 (RPi2/3) usage. Its main goals are to have a small footprint, fast boot times and to reduce the number of writes to the SD card (within reason).

To achieve these goals, sacrifices were made. For example, included language supoort is limited to en_US and security related features such as selinux, auditd and firewalld are disabled or removed. Therefore, it is not advisable to run services that are directly exposed to the internet.

#### Major changes include:
- To facilitate 'out of box' headless support, initial-setup is not run on first boot.
- There is limited 'out of box' hardware support. 'linux-firmware' is not installed by default on the image. You may need to install it for specific 3rd party hardware support (eg. various usb wireless network dongles etc etc).
- Language support is limited to en_US.utf8, all other languages have been stripped from the image to save space.
- All documentation (eg. man pages) from rpm packages have been excluded/stripped from the image.
- SELinux is DISABLED by default.
- Auditd subsystem is DISABLED by default.
- Firewalld is NOT installed.
- Plymouth is NOT installed.
- No swap file is created or enabled by default (you can use [fedberry-config](https://github.com/fedberry/fedberry-config) to create one if needed.
- The / (root) partition is NOT re-sized automatically on first boot (Use [fedberry-config](https://github.com/fedberry/fedberry-config) to do this if required.
- Journaling on the ext4 / (root) partition is disabled.
- /tmp on tmpfs is enabled by default, but is size limited to 100M.
- Journald logs size are limited to 20M.
- Boot options (/boot/cmdline.txt) “elevator=deadline libahci.ignore_sss=1 raid=noautodetect selinux=0 and audit=0” are used by default.

For a detailed list of changes, as compared to other releases, please refer to the fedberry-barebone.ks kickstart file.

**Fedora and the Infinity design logo are trademarks of Red Hat, Inc.*

*^Raspberry Pi is a trademark of the Raspberry Pi Foundation*
