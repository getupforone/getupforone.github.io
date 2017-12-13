---
layout: post
title: "nvidia graphic driver install"
date: "2017-12-13 11:15:00 +0900"
---

maybe it is too late ,but hope can help for others. the follow tips worked for ubuntu 16.04 and elementary os 0.4.

remove all nvidia packages ,skip this if your system is fresh installed

>> sudo apt-get remove nvidia* && sudo apt autoremove

install some packages for build kernel:

>>sudo apt-get install dkms build-essential linux-headers-generic

now block and disable nouveau kernel driver:

>>sudo vim /etc/modprobe.d/blacklist.conf

Insert follow lines to the blacklist.conf:

blacklist nouveau
blacklist lbm-nouveau
options nouveau modeset=0
alias nouveau off
alias lbm-nouveau off

save and exit.

Disable the Kernel nouveau by typing the following commands(nouveau-kms.conf may not exist,it is ok):

>>echo options nouveau modeset=0 | sudo tee -a /etc/modprobe.d/nouveau-kms.conf

build the new kernel by:
>>sudo update-initramfs -u

reboot
