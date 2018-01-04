1. Setup envrionment for droid7.0 on ubuntu16.04
----------------------------------------------------------------------
sudo apt-get install openjdk-8-jdk
sudo apt-get install gnupg flex bison gperf build-essential zip curl
sudo apt-get install gcc-multilib g++-multilib lib32ncurses5-dev lib32z1-dev

2. Build droid7.0 project image
----------------------------------------------------------------------
bootloader:
	cd workspace/xxxdroid-7.0
	source build/envsetup.sh
	lunch
	make clean
	make bootloader -j8

boot:
	make bootimage -j8

system:
	make systemimage -j8

vendor:
	make vendorimage -j8

3. download image by fastboot
----------------------------------------------------------------------
	cdout
	fastboot flash bootloader bootloader.img
	fastboot flash boot boot.img
	fastboot flash vendor vendor.img
	fastboot flash system system.img

