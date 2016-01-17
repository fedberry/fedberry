##Minimal & XFCE Remixes

Both these remixes are close to 'stock' arm releases from Fedora*. Where possible, they endeavor to stick to default Fedora release settings.

##Mini Remix

This remix differs signi cantly from default Fedora settings used for their arm releases. It is a small 'bare bones' remix with some optimisations speci cally tailored towards Rapsberry^ Pi 2 (RPi2) usage. Its main goals are to have a small footprint, fast boot times and to reduce the number of writes to the SD card (within reason).

To achieve these goals, sacrifices have to be made. For example, the only language included is en_US and security related features such as selinux or  rewalld are disabled or removed. Therefore, it is not advisable to run services that are directly exposed to the internet, rather it should be safely tucked away behind a NAT  rewall or something similar.

**Major changes include :**
- To facilitate 'out of box' headless support, initial-setup is not used boot and passwords are set for both 'root' & 'raspberry' users. Please see README.pdf for more information.
- Root logins using sshd are disabled (login via ssh using 'raspberry' user instead).
- There is limited 'out of box' hardware support. 'linux- rmware' is not installed by default on the image. You may need to install it to get speci c hardware support (eg. some wireless
network cards). Please note, it will be pulled in by default when you next update the kernel.
- Only language support for en_US.utf8 is included, all other languages have been stripped
from the image.
- Documentation in rpm packages have been excluded from the image.
- SELinux linux is disabled by default.
- Firewalld is not installed.
- Plymouth is not installed.
- No swap partition is created or enabled by default.
- The / (root) partition is not re-sized automatically at  rst boot.
- Journaling on the ext4 / (root) partition is disabled and 'data=writeback' is enabled.
- /tmp on tmpfs is enabled by default, but is size limited to 100M.
- Journald logs size are limited to 20M.
- Boots options “elevator=deadline libahci.ignore_sss=1 raid=noautodetect” are now used by
default.

For a detailed list of changes, as compared to the 'minimal' & 'xfce releases', please refer to the f23-rpi2-mini-remix.ks kickstart  file.

  *\*Fedora and the Infinity design logo are trademarks of Red Hat, Inc.*
  
  *^Raspberry Pi is a trademark of the Raspberry Pi Foundation*
