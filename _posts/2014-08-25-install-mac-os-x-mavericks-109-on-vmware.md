---
layout: post
title: "Install Mac OS X Mavericks 10.9 on VMware"
description: "My experience on installing Mac OS X on VMware Workstation"
category: notes
tags: [OS X, VMware, VMtools, fullscreen]
---

This weekend I was struggling on how to install the Mac OS X Mavericks 10.9 on VMware in Windows 7 for my girlfriend. The overall process is not so difficult, you can definitely find quite a lot of guidelines on the Internet. Here I will note down some important points.

- Check if your computer supports Hardware VT

   To install Mac OS X on VMware, you must first confirm that you computer's CPU supports Hardware Virtualization Technology and enable it from BIOS settings. I think most laptops currently in use should support it.

- Install VMtools on OS X

   VMtools should be installed as it can enable direct copy-paste action from host machine to the virtual machine, which is one of the advantage of VMware over VirtualBox. To install VMtools, you need to download a darwin.iso, load it to the CD/DVD drive. The VM should be able to detect and load it on destop automatically.

- Configure Fullscreen support for OS X

   This is the most tedious part through the whole installation. As the host machine's display resolution is 1366x768, which cannot be found in the Mac OS X dislay setting, resulting two dark areas beside the OS X screen. To solve the problem I googled a lot and some solutions are listed below.

   1. Install [VMsvga 2](http://sourceforge.net/projects/vmsvga2/files/) and more resolution settings will appear in the drop-down box. I tried and failed, there is no change on the display setting.
   
   2. Change `/Library/Preferences/SystemCOnfiguration/com.apple.boot.plist` file, which I did not try as I thought changing the configuration file is not safe and should the last option.
   
   3. Follow the answer [here](http://nickology.com/2013/11/21/displaylink-mavericks-osx-10-9-resolution-display-fix/), I simply press `alt` and click the Scaled option. Then magic happens! I see more resultion settings appear Problem solved! Honestly I do not understand why it works as I am really a Mac OS X noob. If anyone knows the mechanism behind please leave a comment below.

In the end, I would like to conclude that it might not be suitable to conduct ios development on virtual machine. If you really want to be an ios app developer, consider to go and buy a Mac:) I am not advertising for Apple!
