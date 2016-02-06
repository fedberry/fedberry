##SD CARD INSTALLATION
Download images here: [http://download.fedberry.org](http://download.fedberry.org/releases/)

The image can be installed using the Unix/Linux dd command.

###Requirements:
- A computer running some form of Unix or Linux.
- A minimum 2GB SD card is required for the 'mini' image install.
- A 4GB SD card is recommended for 'minimal' image installs.
- A 8GB SD card is recommended for all other disk images.
- A SD/SDHC card writer, either built in to the computer or connected to a USB port.

###Steps:

1.  Download the image and ensure you have not got a corrupted disk image by running sha256sum on the file and checking it against provided checksums.
    
    For example:
    
    ```$ sha256sum fedora-23-remix-rpi2-minimal-1.raw.xz```
    
    OR
    
    ```$ sha256sum -c fedora-23-remix-rpi2.CHECKSUM```

2.  Insert your sd card and determine which device node has been assigned to your media. Read /var/log/messages or run 'dmesg' 'to learn which device was assigned to your media (this will be something like /dev/sdc or /dev/mmcblk0).

3.  As root user or 'sudo', use 'dd' to write the disk image to your SD card.

    PLEASE NOTE that the use of the 'dd' tool can overwrite ANY partition on your computer. If you specify the wrong device you could delete all your existing linux partitions. Make sure you KNOW what you are doing here otherwise don't do it or ask someone else who does! Please be VERY careful!
    
    Ensure the device is unmounted then copy the image file to the card: xzcat NameOfImageFile | dd of=/dev/DeviceNode
    
    For example:
    
    ```$ xzcat fedora-23-remix-rpi2-minimal-1.raw.xz | dd of=/dev/sdc```
    
4.  Run 'sync'; this will ensure the write cache is flushed and that it is safe to unmount and remove your SD card from the card reader.
 
