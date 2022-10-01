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
and
https://blog.csdn.net/shengnan_wu/article/details/8142996

1. Download https://cfhcable.dl.sourceforge.net/project/sunsea1026/work/arm-linux-gcc-4.3.2.tgz
2. tar -xvzf arm-linux-gcc-4.3.2.tgz
3. move the extracted folder to /usr/local/arm/3.4.1/bin/arm-linux-gcc 

===============================================================================================================

Compiling Uboot for S3C2440A
1. Download Uboot source code @ http://ftp.denx.de/pub/u-boot/u-boot-2009.08.tar.bz2
   a. tar -jxvf u-boot-2009.08.tar.bz2

2. Preparing 2440 code
   a. cd uu-boot-2009.08/board/samsung/
   b. mkdir my2440
   d. cp -rf smdk2410/* my2440/
   e. cd my2440
   f. mv smdk2410.c my2440.c
   g. cd ../../../
   h. cp include/configs/smdk2410.h include/configs/my2440.h
 
3. Preparing the Makefile
   a. gedit board/samsung/my2440/Makefile
   b. COBJS := my2440.o flash.o
   c. CROSS_COMPILE ?= arm-linux-
   d. smdk2410_config    :    unconfig   //2410编译选项格式
        @$(MKCONFIG) $(@:_config=) arm arm920t smdk2410 samsung s3c24x0
   e. my2440_config    :    unconfig     //2440编译选项格式
        @$(MKCONFIG) $(@:_config=) arm arm920t my2440 samsung s3c24x0
   Note :-
      arm920t : CPU type
      my2440  : target folder under board/
      samsung : subfolder under board/ , this can be NULL if my2440 is created direct under board/
      s3c24x0 : CPY model
      * use tab for each second line to avoid compilaiton error
 
4. Compiling
   a. make my2240_config
   b. make
   * after compilation completed, there will be a file : u-boot.bin
