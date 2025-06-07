# SCSI2SD SD Card Setup Guide For The AKAI MPC2000
#### Version 1.0 · April 23, 2025
#### Created by BDAC · © bootdiskandchill, 2025

## Overview

If you're using a SCSI2SD, this is your guide to setting up SD cards for the MPC2000. I'll cover a basic setup with a single partition, and an advanced setup with multiple disks that requires flashing the SCSI2SD.

## Requirements

- For basic setup: SD card, macOS
- For advanced setup: SD card, USB data cable, macOS, and the [SCSI2SD-Util app](https://docs.scsi2sd.com)

## Basic Setup (Default SCSI2SD Settings)

1. Insert the SD card into a USB reader or adapter on your Mac and open a terminal

2. Type `diskutil list` to display all connected drives
   - Look for your SD card (e.g., `/dev/disk5 (external, physical)`)
   - Note the disk number (e.g., disk5) - yours will likely be different

3. Erase the card:
   ```
   sudo diskutil eraseDisk FAT32 SDCARD GPTFormat /dev/disk5
   ```
   - Make sure to use the correct disk number for your system
   - You'll need to enter your admin password

4. Eject the card:
   ```
   diskutil unmountDisk disk5
   ```
   - Use your specific disk number

5. Remove the SD card. Boot your MPC with a floppy disk, format the partition on the MPC, and copy the OS to the SCSI2SD partition on SCSI-0
   - This creates a bootable partition

#### OR

6. After running the command to eject the card, do not remove it. Download the [BDAC Sound Library Remix](https://bootdiskandchill.com) or MPC2000 Setup Partition. Run the command:
   ```
   sudo dd if=mp2kcd.iso of=/dev/disk5s2
   ```
   - Use your specific disk number and enter your password
   - This command loads the MPC Sound Library onto the partition
   - Use this technique to load your own ISO files to the card
   - Works for Akai format sample CDs too

7. Remove the SD card. Boot your MPC with the SCSI2SD

#### Basic Setup Complete

You can now transfer files between the SD card and your PC/Mac
   - For cross-compatibility, only use the SCSI-0 device and the A partition
   - You may be able to format and use SCSI-1, SCSI-2, and SCSI-3, depending on your SCSI2SD settings, but compatibility issues may occur

## Advanced Setup (Custom SCSI2SD Settings)

1. Insert the SD card into a USB reader or adapter on your Mac and open a terminal

2. Type `diskutil list` to display all connected drives
   - Look for your SD card (e.g., `/dev/disk5 (external, physical)`)
   - Note the disk number (e.g., disk5) - yours will likely be different

3. Erase the card:
   ```
   sudo diskutil eraseDisk FAT32 SDCARD GPTFormat /dev/disk5
   ```
   - Make sure to use the correct disk number for your system
   - You'll need to enter your admin password

4. Partition the card:
   ```
   diskutil partitionDisk /dev/disk5 MS-DOS HD_1 700M MS-DOS HD_2 900M MS-DOS HD_3 900M MS-DOS HD_4 900M MS-DOS EXTRA 200M MS-DOS NO_NAME R
   ```
   - Double-check the disk number before running the command
   - You will receive an error; disregard it

5. Eject the card:
   ```
   diskutil unmountDisk disk5
   ```
   - Use your specific disk number

6. Remove the SD card. Boot your MPC with a floppy disk, format the partitions on the MPC, and copy the OS to the SCSI2SD partition on SCSI-0
   - This creates 4 bootable partitions

#### OR

7. After running the command to eject the card, do not remove it. Download the BDAC Sound Library Remix or MPC2000 Setup Partition. Run the command:
   ```
   sudo dd if=mp2kcd.iso of=/dev/disk5s2
   ```
   - Use your specific disk number and enter your password
   - This command loads the MPC Sound Library onto the first partition
   - This will let you format the other partitions in the MPC
   - Use this technique to load your own ISO files to the card
   - Repeat for disk#s3, s4, etc. as needed
   - Works for Akai format sample CDs too

8. Remove the SD card. Boot your MPC with the SCSI2SD

#### Advanced Setup Complete

You can now transfer files between the SD card and your PC/Mac
   - For cross-compatibility, only use the A partition when transferring files
   - You can format and use SCSI-1, SCSI-2, and SCSI-3, depending on your SCSI2SD settings with no compatibility issues

## Flashing the SCSI2SD

It is essential to flash the SCSI2SD in order to use all 4 virtual disks.

1. Connect the SCSI2SD to your Mac with the USB data cable and run the SCSI2SD-Util app
   - Click on the terminal running the app to use it

2. Select "Open File" in the File menu and load the BDAC mp2k.xml setup file

3. Select "Save to device" in the File menu to flash the SCSI2SD
   - The orange LED will flash during programming (about 30 seconds)
   - When complete, disconnect the SCSI2SD from your computer

4. Quit the SCSI2SD-Util app and load the SD card into the SCSI2SD

5. Boot the MPC with the SCSI2SD
   - The SCSI2SD can emulate a maximum of 4 drives
   - Virtual disks will appear as SCSI-0, SCSI-1, SCSI-2, and SCSI-3
