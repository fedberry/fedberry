# ![fedberry](https://avatars2.githubusercontent.com/u/16729488?v=3&s=40) FedBerry 24 - Fedora Remix for Raspberry Pi 2/3

## IMPORTANT INFORMATION

These are Fedora® Remix disk images specifically built for use with the Raspberry Pi® 2/3 Model B computers. These disk images are unofficial Fedora Remixes and are not afiliated, provided or supported by the Fedora Project. Official, unmodified Fedora software is available through the Fedora Project website http://fedoraproject.org. *^

##Installation
Download images here: [http://download.fedberry.org](http://download.fedberry.org/releases/)

Please read [INSTALL.md](https://github.com/fedberry/fedberry/blob/master/INSTALL.md)

##First Boot

####XFCE & LXQt release images
The root partition is automatically re-sized on the first boot. After automatically rebooting the graphical 'initial-setup' utility will start. Failure to complete the initial-setup will prevent logging into the system.

####Minimal release image
The root partition is automatically re-sized on the first boot. After automatically rebooting and if headless mode is not enabled, the serial console 'initial-setup' utility will start. If headless mode is enabled, log in using the default root user password at the login prompt.

####Barebone release image
The root partition is NOT automatically re-sized at boot due to boot time and image size considerations. The initial-setup utility is not used for this release. You can optionally use fedberry-config to resize the root partition after booting.

##Default Password

####XFCE & LXQt release images
No root user password (or users) are set by default. After the initial OS boot, please set the timezone, root password and create users when prompted at initial setup.

####Minimal image
To facilitate optional headless support, a root user password is already set. After the initial OS boot, please set the timezone, root password and create users when prompted at initial setup. If you choose not to change the root user password using initial-setup (eg. you initially boot using headless mode), then you will be prompted to change it at first login. 

####Barebone release image
To facilitate default headless support, a root user password is already set. You will be prompted to change your root password when you first login.

**Root password = fedberry**

##Additional or Modified Software
Yum repositories are located here: [http://download.fedberry.org/releases/](http://download.fedberry.org/releases/)

As this is a Fedora Remix, some additional or modified RPMs are included to enable full compatibility with the BCM2836/7 SOCs (RPi2/3) or to add extra features. The most significant change is a custom kernel. The included kernel has vanilla kernel.org sources patched with modications from the Raspberry Pi foundation's kernel tree (bcm2709 port). Refer here: https://github.com/raspberrypi/linux.

All software sources for the RPMs can be found in our githib repositories (https://github.com/fedberry) or the provided SRPMs here: http://download.fedberry.org/releases/

##DISCLAIMER
**All software provided on this site are being offered for FREE in hopes that they will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. Use at your OWN RISK AND WE DISCLAIM LIABILITY FOR ANY DAMAGES RESULTING FROM ITS USE.**

**Fedora and the Infinity design logo are trademarks of Red Hat, Inc.*

*^Raspberry Pi is a trademark of the Raspberry Pi Foundation*
   
