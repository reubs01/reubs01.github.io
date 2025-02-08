---
title: "Displaying connected drives + bitlocker"
layout: post
---

The following script retrieves information about all connected disk drives using the Win32_DiskDrive WMI class. It outputs key details such as the drive ID, model, media type, serial number and size (converted to GB). 

You can find the code [here](https://github.com/reubs01/displayDriveInfo).

Useful if used with the following (see [here](https://github.com/reubs01/checkBitlocker)) which retrieves all mounted volumes and checks their BitLocker encryption status using manage-bde -status.
