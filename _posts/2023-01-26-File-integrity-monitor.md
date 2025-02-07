---
title:  "A file integrity monitor with powershell"
layout: post
---

A file integrity monitor (FIM) is a powerful security tool that detects and alerts on any changes made to important files on a computer or network. This includes changes to the contents of a file as well as changes to the file's attributes such as permissions, ownership, and timestamps. FIMs work by creating a baseline or "fingerprint" of important files, which is used as a reference point to compare against any changes that occur. If a change is detected, the FIM can alert the system administrator or take other actions to mitigate potential security threats.

### How the code works

My code is specifically designed to detect changes to files and configurations by utilizing the following process:

![title](/fim-chart.jpg)

### The step by step process:

* The user is prompted to decide whether they want to collect a new baseline or begin monitoring files with a saved baseline.
* If collecting a new baseline, any existing one is deleted and the process begins by calculating the hashes of the target files in a specific directory. The calculated hash is then written to the baseline.txt file, creating the new baseline.
* If monitoring with a saved baseline, the files and their corresponding hash are loaded from the baseline and stored in a dictionary.
* The files are then continuously monitored against the saved baseline by comparing the calculated hashes against the dictionary. This allows for the detection of new files, changes to existing files, and deleted files.

You can find the code repository [here](https://github.com/reubenbaulch/fileIntegrityMonitor).
