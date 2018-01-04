1. Setup envrionment for droid7.0 on ubuntu16.04
----------------------------------------------------------------------
sudo apt-get install openjdk-8-jdk
sudo apt-get install gnupg flex bison gperf build-essential zip curl

2. Build droid7.0 project
----------------------------------------------------------------------
bootloader:
	cd workspace/xxxdroid-7.0
	source build/envsetup.sh
	lunch
	make clean
	make bootloader -j8

bootimage:
	make bootimage -j8
