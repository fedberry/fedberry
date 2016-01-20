##Minimal & XFCE Remixes

Both these remixes are close to 'stock' arm releases from Fedora*. Where possible, they endeavor to stick to default Fedora release settings.

##Mini Remix

This remix differs significantly from default Fedora settings used in their arm releases. It is a small 'bare bones' remix with some optimisations specifically tailored towards Rapsberry^ Pi 2 (RPi2) usage. Its main goals are to have a small footprint, fast boot times and to reduce the number of writes to the SD card (within reason).

To achieve these goals, sacrifices were made. For example, included language supoort is limited to en_US and security related features such as selinux or firewalld are disabled / removed. Therefore, it is not advisable to run services that are directly exposed to the internet, rather it should be safely tucked away behind a NAT firewall or something similar.

**Major changes include :**
- To facilitate 'out of box' headless support, initial-setup is not run on first boot and passwords are set for both 'root' & 'raspberry' users. Please see README for more information.
- Root logins using sshd are disabled (login via ssh using 'raspberry' user instead).
- There is limited 'out of box' hardware support. 'linux-firmware' is not installed by default on the image. You may need to install it for specific hardware support (eg. various wireless network cards). Please note, linux-firmware will be installed by default with a kernel update.
- Language support is limited to en_US.utf8, all other languages have been stripped from the image to save space.
- Documentation in rpm packages have been excluded from the image.
- SELinux is disabled by default.
- Firewalld is not installed.
- Plymouth is not installed.
- No swap partition is created or enabled by default.
- The / (root) partition is NOT re-sized automatically on first boot.
- Journaling on the ext4 / (root) partition is disabled and 'data=writeback' is enabled.
- /tmp on tmpfs is enabled by default, but is size limited to 100M.
- Journald logs size are limited to 20M.
- Boot options (cmdline.txt) “elevator=deadline libahci.ignore_sss=1 raid=noautodetect” are now used by default.

For a detailed list of changes, as compared to the 'minimal' & 'xfce releases', please refer to the f23-rpi2-mini-remix.ks kickstart file.

**Fedora and the Infinity design logo are trademarks of Red Hat, Inc.*

*^Raspberry Pi is a trademark of the Raspberry Pi Foundation*
