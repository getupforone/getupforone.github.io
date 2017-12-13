---
layout: post
title: "cuda toolkit intstall"
date: "2017-12-13 13:44:08 +0900"
---
$sudo apt-get install build-essential
$sudo apt-get install linux-headers-$(uname -r)
$sudo apt-get install dkms

 Create the /etc/modprobe.d/blacklist-nouveau.conf file with :

blacklist nouveau
options nouveau modeset=0

$sudo update-initramfs -u
$sudo reboot

The NVIDIA CUDA Toolkit is available at http://developer.nvidia.com/cuda-downloads.

Use the following command to uninstall a Toolkit runfile installation:

$sudo /usr/local/cuda-X.Y/bin/uninstall_cuda_X.Y.pl

Perform the pre-installation actions.

Disable the Nouveau drivers.

change mode to text mode with key  ctrl+alt+f1

$sudo chmod a+x cuda_xxx.run

I run the CUDA driver run file.
*Notice that I explicitly don't want the OpenGL flags to be installed*

$sudo cuda_xxx.run --no-opengl-libs

Accept EULA conditions
Say YES to installing the NVIDIA driver
SAY YES to installing CUDA Toolkit + Driver
Say YES to installing CUDA Samples

Say NO rebuilding any Xserver configurations with Nvidia.


$ls /dev |  grep nvidia

if they don't,do:
sudo modprobe nvidia

$ export PATH=/usr/local/cuda-7.0/bin:$PATH
$ export LD_LIBRARY_PATH=/usr/local/cuda-7.0/lib64:$LD_LIBRARY_PATH

Verify the driver version:
$ cat /proc/driver/nvidia/version

Check CUDA driver version:
$ nvcc -V

The reboot is required to completely unload the Nouveau drivers and prevent the graphical interface from loading. The CUDA driver cannot be installed while the Nouveau drivers are loaded or while the graphical interface is active.

Verify that the Nouveau drivers are not loaded. If the Nouveau drivers are still loaded, consult your distribution's documentation to see if further steps are needed to disable Nouveau.

Run the installer and follow the on-screen prompts:
$ sudo sh cuda_<version>_linux.run


Read more at: http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#ixzz5175sJDbP
Follow us: @GPUComputing on Twitter | NVIDIA on Facebook
Read more at: http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#ixzz5175Fu24W
Follow us: @GPUComputing on Twitter | NVIDIA on Facebook
ref1 : http://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#pre-installation-actions
ref2 :
https://devtalk.nvidia.com/default/topic/878117/cuda-setup-and-installation/-solved-titan-x-for-cuda-7-5-login-loop-error-ubuntu-14-04-/
