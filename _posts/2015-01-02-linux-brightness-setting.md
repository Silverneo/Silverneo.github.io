---
layout: post
title: Linux brightness setting
categroy: linux
tags: [linux, brightness, mint]
---

Struggling for my final year project, finally I decided to install Linux OS. I installed Linux Mint 15 in my laptop before. However, after I finished the previous programming project, I switched back to Windows 7 and totally throw it away. This time I decided to install Linux Mint 17.1 Rebecca Xfce version.

I have never used Xfce edition before. Usually I will choose the common mate or Connamon one. This time I want to try something new so I choose Xfce. Again, the installation is quite straightforward. I updated the system, followed the guidelines in this webpage [10 things to do first in Linux Mint 17.1 Xfce](https://sites.google.com/site/easylinuxtipsproject/8) and entered the system. Everything seems to be perfect!

But wait, why I cannot control my screen Brightness!? My laptop is an old Lenovo Y450 with Nvidia Graphics, and I believed I encountered this kind of problem before. So I start searching the Internet. Most answers seems to be like this

> Edit the /etc/default/grub file
>
> Change GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" to
>
> GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_backlight=vendor acpi_osi=Linux"
>
> Update the grub with `sudo update-grub` and reboot

However, it does not work for my Laptop!! It really makes me crazy!! Then I found this [ANSWER](http://unix.stackexchange.com/a/163236/101348) from stackoverflow. It seems worth to have a try. But wait! Where is the /etc/X11/xorg.conf file!!! I cannot find the file :((( Luckily I figured out a way to get the file. Go to `NVIDIA X Server Settings`, Click `X Server Display Configuration` and click the `Save to X Configuration File` then quit. the xorg.conf file is there!

Next, I just followed the answer mentioned above, edited the file as below.

{% highlight bash %}

Section "Device"
    Identifier     "Device0"
    Driver         "nvidia"
    VendorName     "NVIDIA Corporation"
    BoardName      "GeForce G210M"
    Option         "RegistryDwords" "EnableBrightnessControl=1"
EndSection

{% endhighlight %}
Now I can adjust the screen brightness without any problem!
