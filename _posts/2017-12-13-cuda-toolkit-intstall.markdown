---
layout: post
title: "cuda toolkit intstall"
date: "2017-12-13 13:44:08 +0900"
---

$sudo apt-get install linux-headers-$(uname -r)
$sudo apt-get install dkms

The NVIDIA CUDA Toolkit is available at http://developer.nvidia.com/cuda-downloads.

Use the following command to uninstall a Toolkit runfile installation:

$sudo /usr/local/cuda-X.Y/bin/uninstall_cuda_X.Y.pl

Perform the pre-installation actions.

Disable the Nouveau drivers.

Reboot into text mode  ctrl+alt+f1


The reboot is required to completely unload the Nouveau drivers and prevent the graphical interface from loading. The CUDA driver cannot be installed while the Nouveau drivers are loaded or while the graphical interface is active.

Verify that the Nouveau drivers are not loaded. If the Nouveau drivers are still loaded, consult your distribution's documentation to see if further steps are needed to disable Nouveau.

Run the installer and follow the on-screen prompts:
$ sudo sh cuda_<version>_linux.run


Read more at: http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#ixzz5175sJDbP
Follow us: @GPUComputing on Twitter | NVIDIA on Facebook
Read more at: http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#ixzz5175Fu24W
Follow us: @GPUComputing on Twitter | NVIDIA on Facebook
ref http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#pre-installation-actions
