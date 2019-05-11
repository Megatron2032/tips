# Ubuntu login loop after nvidia driver installation

## Solution
#### 
* sudo apt-get remove --purge nvidia-*  
sudo apt-get autoremove  

####
* sudo vim /etc/modprobe.d/blacklist-nouveau.conf  
\# add following lines：  
  blacklist nouveau  
  options nouveau modeset=0  
\# then excute this:  
sudo update-initramfs -u  

####
* sudo service lightdm stop  
sudo chmod +x NVIDIA-xxx.run  
\# use _sudo ./NVIDIA-xxx.run -A_ to check advanced options  
sudo ./NVIDIA-xxx.run **--no-opengl-files**  
\# then choose No when asked whether to modify xorg.conf file  

####
* reboot


## References

[1] <https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html>  
[2] <https://devtalk.nvidia.com/default/topic/878117/cuda-setup-and-installation/-solved-titan-x-for-cuda-7-5-login-loop-error-ubuntu-14-04-/>  

