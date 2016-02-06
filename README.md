# ![fedberry](https://avatars2.githubusercontent.com/u/16729488?v=3&s=40) FedBerry - Fedora Remix for Raspberry Pi 2

## IMPORTANT INFORMATION

These are Fedora® Remix disk images specifically built for use with the Raspberry Pi® 2 (RPi2) computer. These disk images are unofficial Fedora Remixes and are not afiliated, provided or supported by the Fedora Project. Official, unmodified Fedora software is available through the Fedora Project website http://fedoraproject.org. *^

##Installation
Download images here: [http://download.fedberry.org](http://download.fedberry.org/releases/)

Please read [INSTALL.md](https://github.com/fedberry/fedberry/blob/master/INSTALL.md)

##First Boot

####Minimal and XFCE release images

The root partition is automatically re-sized when the OS is first booted. After re-sizing, it will automatically reboot. After rebooting the system will launch the 'initial-setup' utility. For graphical images this will occur on the display, for minimal images this will occur on the serial console. Failure to complete the initial-setup will prevent logging into the system.

####Mini release image
The root partition is NOT automatically re-sized at boot due to boot time and image size considerations. The initial-setup utility is not used for this release.

##Default User / Passwords

####Minimal and XFCE release images
No root password or users are set by default. After the initial OS boot, please set the timezone, root password and create users when prompted at initial setup.

####Mini release image
To facilitate default headless support, a root user password is already set. Please remember to change the root password after the first boot.

**Root password = fedberry**

A default user of 'raspberry' is also created but password change is required after the first login.

**User password = raspberry**

##Additional or Modified Software
Our Yum repository is located here: [https://vaughan.fedorapeople.org](https://vaughan.fedorapeople.org)

As this is a Fedora Remix, some additional or modified RPMs are included to enable full compatibility with the BCM2836 SOC (RPi2) or to add extra features. The most significant change is a custom kernel. The included kernel has vanilla kernel.org sources patched with modications from the Raspberry Pi foundation's kernel tree (bcm2709 port). Refer here: https://github.com/raspberrypi/linux.

All software sources for the RPMs can be found in our githib repositories (https://github.com/fedberry) or the provided SRPMs here: https://vaughan.fedorapeople.org/fed23/SRPMS

##DISCLAIMER
**All software provided on this site are being offered for FREE in hopes that they will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. Use at your OWN RISK AND WE DISCLAIM LIABILITY FOR ANY DAMAGES RESULTING FROM ITS USE.**

**Fedora and the Infinity design logo are trademarks of Red Hat, Inc.*

*^Raspberry Pi is a trademark of the Raspberry Pi Foundation*
   
