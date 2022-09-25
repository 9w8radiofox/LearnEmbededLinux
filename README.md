LearnEmbededLinux

1. Setting up Arm cross-compiler toolchain in Ubuntu
 
a. Download 
https://releases.linaro.org/components/toolchain/binaries/4.9-2017.01/arm-linux-gnueabihf/
gcc-linaro-4.9.4-2017.01-x86_64_arm-linux-gnueabihf.tar.xz

b. create folder 
/usr/local/arm

c. copy downloaded tar.xz to /usr/local/arm/
sudo cp gcc-linaro-4.9.4-2017.01-x86_64_arm-linux-gnueabihf.tar.xz /usr/local/arm/ -f

d. unzip the tar.xz
sudo tar -vxf gcc-linaro-4.9.4-2017.01-x86_64_arm-linux-gnueabihf.tar.xz

e. append /etc/profile
export PATH=$PATH:/usr/local/arm/gcc-linaro-4.9.4-2017.01-x86_64_arm-linux-gnueabihf/bin

f. restart Ubuntu

g. install required library
sudo apt-get install lsb-core lib32stdc++6

h. check installation 
arm-linux-gnueabihf-gcc -v

===============================================================================================================

Another set from 
https://developer.aliyun.com/article/538636?spm=a2c6h.13813017.content3.22.4f3f42d9SzkXoK
and
https://blog.csdn.net/zhengqijun_/article/details/65440908
and 
https://blog.csdn.net/nitonggui/article/details/115816983

1. Download https://cfhcable.dl.sourceforge.net/project/sunsea1026/work/arm-linux-gcc-4.3.2.tgz
2. tar -xvzf arm-linux-gcc-4.3.2.tgz
3. move the extracted folder to /usr/local/arm/3.4.1/bin/arm-linux-gcc 
4. 


