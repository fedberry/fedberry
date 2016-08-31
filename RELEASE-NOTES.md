##Minimal & XFCE Remixes

Both these remixes are close to 'stock' arm releases from Fedora*. Where possible, they endeavor to stick to default Fedora release settings. Major differences are:
- The use of swap files in lieu of swap partitions.
- Having /tmp on tmpfs is enabled but size limited to 100M.
- The root partition is automatically set to resize on first boot.
- To facilitate optional headless booting, a default root password (fedberry) is set in the 'minimal' release.


##Barebone Remix

This release is for ADVANCED users only, as it differs significantly from standard default Fedora arm releases. As the name suggests, it is a small 'bare bones' remix with some optimisations specifically tailored towards Rapsberry^ Pi 2/3 (RPi2/3) usage. Its main goals are to have a small footprint, fast boot times and to reduce the number of writes to the SD card (within reason).

To achieve these goals, sacrifices were made. For example, included language supoort is limited to en_US and security related features such as selinux, auditd and firewalld are disabled or removed. Therefore, it is not advisable to run services that are directly exposed to the internet.

####Major changes include:
- To facilitate 'out of box' headless support, initial-setup is not run on first boot.
- There is limited 'out of box' hardware support. 'linux-firmware' is not installed by default on the image. You may need to install it for specific hardware support (eg. various wireless network cards). Please note, linux-firmware will be re-installed by default with a kernel update.
- Language support is limited to en_US.utf8, all other languages have been stripped from the image to save space.
- All documentation (eg. man pages) from rpm packages have been excluded/stripped from the image.
- SELinux is disabled by default.
- Auditd subsystem is disabled by default.
- Firewalld is not installed.
- Plymouth is not installed.
- No swap file is created or enabled by default.
- The / (root) partition is NOT re-sized automatically on first boot.
- Journaling on the ext4 / (root) partition is disabled and 'data=writeback' is enabled.
- /tmp on tmpfs is enabled by default, but is size limited to 100M.
- Journald logs size are limited to 20M.
- Boot options (/boot/cmdline.txt) “elevator=deadline libahci.ignore_sss=1 raid=noautodetect selinux=0 and audit=0” are used by default.

For a detailed list of changes, as compared to other releases, please refer to the fedberry-barebone.ks kickstart file.

**Fedora and the Infinity design logo are trademarks of Red Hat, Inc.*

*^Raspberry Pi is a trademark of the Raspberry Pi Foundation*
