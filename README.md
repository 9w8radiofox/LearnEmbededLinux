# LearnEmbededLinux

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
