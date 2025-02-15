---
title:  "Extract bitLocker recovery keys for mounted volumes"
layout: post
---

This PowerShell script scans all mounted volumes, detects BitLocker-encrypted drives, and extracts their recovery keys. If a drive is not protected by BitLocker, it notifies the user. The script then allows the user to save the extracted keys to a CSV file via a simple GUI-based file picker.
