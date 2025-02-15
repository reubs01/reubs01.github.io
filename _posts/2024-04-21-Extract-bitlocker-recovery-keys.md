---
title:  "Dumping bitlocker recovery keys"
layout: post
---

This powershell script scans all mounted volumes, detects bitlocker encrypted drives and extracts their recovery keys. If a drive is not protected by bitlocker, it notifies the user. The script then allows the user to save the extracted keys to a CSV via a simple GUI based file picker.

You can find the code [here](https://github.com/reubs01/dumpBitlockerKeys).
