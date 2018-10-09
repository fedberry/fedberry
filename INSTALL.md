## FEDBERRY IMAGE INSTALLATION
Download images here: [http://download.fedberry.org](http://download.fedberry.org/releases/)

### Requirements:
- A computer running some form of Linux/Unix or Windows.
- A minimum 4GB SD card or USB mass storage device (MSD) is recommended for 'barebone' & 'minimal' image installs.
- A minimum 8GB SD card or USB MSD is recommended for all other disk images.
- A SD/SDHC card writer, either built in to the computer or connected to a USB port.


### Install Images using a Linux/Unix OS

The image can be installed using the Unix/Linux dd command.

1.  Download the image and ensure you have not got a corrupted disk image by running sha256sum on the file and checking it against provided checksums.

    For example:
    ```
    $ sha256sum -c fedberry-27.1.CHECKSUM.asc
    ```
2.  Insert your sd card or USB mass storage device (MSD) and determine which device node has been assigned to your media. Read /var/log/messages or run 'dmesg' 'to learn which device was assigned to your media (this will be something like /dev/sdc or /dev/mmcblk0).

3.  As root user or 'sudo', use 'dd' to write the disk image to your SD card or USB MSD.

    PLEASE NOTE that the use of the 'dd' tool can overwrite ANY partition on your computer. If you specify the wrong device you could delete all your existing linux partitions. Make sure you KNOW what you are doing here otherwise don't do it or ask someone else who does! Please be VERY careful!
    
    Ensure the device is unmounted then copy the image file to the SD card / USB MSD: xzcat NameOfImageFile.raw.xz | dd bs=1M of=/dev/DeviceNode status=progress
    
    For example:
    ```
    $ xzcat fedberry-minimal-27.1.raw.xz |dd bs=1M of=/dev/sdc status=progress
    ```
    
4.  Run 'sync'; this will ensure the write cache is flushed and that it is safe to unmount and remove your SD card / USB MSD.
    ```
    $ sync
    ```

5.   Remove the SD card from the card reader and use it to boot FedBerry on your RPi2/3


### Boot From a USB Mass Storage Device on a RPi3
FedBerry supports booting your RPi3 directly from a USB mass storage device (MSD) such as a flash or USB hard drive. This feature is experimental and may not work with all USB mass storage devices. You will need to firstly enable (program) the USB boot mode by following instructions [HERE](https://www.raspberrypi.org/documentation/hardware/raspberrypi/bootmodes/msd.md).

Once the RPi3 USB boot mode is enabled, simply copy the desired FedBerry release image to your USB flash/hard drive (as per above instructions) and then boot FedBerry on your RPi3. Please note: There is no need to prepare or modify Fedberry release images once copied to your USB MSD. For further reading on RPi boot modes, please read [here](https://www.raspberrypi.org/documentation/hardware/raspberrypi/bootmodes/).


### Install Images using Windows

1.  Extract the downloaded fedberry xz compressed raw image. You can use a file archiver such as [7-zip](http://www.7-zip.org) to extract xz files under Windows.

2.  Download the Win32DiskImager utility from the [Sourceforge Project](http://sourceforge.net/projects/win32diskimager/).

3.  Insert the SD card into your SD card reader and check which drive letter was assigned. You can easily see the drive letter, such as ```G:```, by looking in the left column of Windows Explorer. You can use the SD card slot if you have one, or a SD adapter in a USB port.

4.  Extract the executable from the Win32DiskImager zip file and run the Win32DiskImager utility. You may need to run this as administrator; right-click on the file and select Run as administrator.

5.  Select the raw fedberry image file you extracted in step 1.

6.  Select the drive letter of the SD card in the device box. WARNING: Be careful to select the correct drive. If you get the wrong drive you can destroy data on your computer's hard disk. If you are using an SD card slot in your computer and can't see the drive in the Win32DiskImager window, try using an external SD adapter.

7.  Click 'Write' and wait for the process to complete.

8.  Exit Win32DiskImager, remove the SD card and use it to boot FedBerry on your RPi2/3.
