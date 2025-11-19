---
title: "Win98Setup"
source: "Win98Setup.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "WIN 98 SETUP FDISK.EXE and FORMAT.EXE ------------------------ FDISK and FORMAT are utilities necessary for installing a new hard disk in your..."
long_description: "FDISK.EXE and FORMAT.EXE ------------------------"
---



WIN 98 SETUP


FDISK.EXE and FORMAT.EXE
------------------------

FDISK and FORMAT are utilities necessary for installing a new hard  disk  in
your computer or for starting over fresh with a clean disk.  FDISK  is  used
first to create a partition and then FORMAT is used to  make  the  partition
available for use. FDISK.EXE is found on the Win98 setup boot  disk.  Format
.exe is not initially on the floppy disk, it is  included  as  part  of  the
RAMDrive 2MB partition temporarily created by setup.  Copy  format.exe  from
the RAMDrive to the floppy.

WARNING: Using FDISK incorrectly can destroy all data on your hard disk.  If
you are unsure of how to use FDISK, consult your computer documentation.

You can use the Windows 98 version of FDISK to create  FAT32  partitions  on
drives over 512 megabytes in size. FAT32 reduces the cluster size for  large
drives and allows you to create single partitions on drives over 2 GB.
To view your current drive status, type FDISK /STATUS at the MS-DOS  command
prompt.

After you have partitioned a drive using FDISK, you will  need  to  use  the
FORMAT command. To format a newly partitioned drive, type:

      FORMAT X:

Where X represents the letter of the drive that you want to format.

If you want to format drive C, you need to make this disk a system  disk  so
that your computer can start. To do this, type /s at the end of  the  FORMAT
command. For example:

      FORMAT C: /s

System Startup files will  be  automatically  copied  after  your  drive  is
formatted.




Multi-Config Start Menu

==========================
If you boot your computer using the new Windows  98  Startup  Disk,  a  boot
menu appears allowing you the option to load drivers for the most common CD-
ROM drives or perform a normal clean boot.
After you make your selection, the Config.sys file loads the appropriate CD-
ROM driver (if selected) and then loads a  2MB  RAMDrive.  The  RAMDrive  is
used to store all the diagnostic tools necessary to  troubleshoot  the  most
common problems.

*Note*
The RAMdrive may cause your CD-Rom to pushed back 1 drive  letter.  If  your
CD-Rom is usually drive D:, it will now be Drive E:

