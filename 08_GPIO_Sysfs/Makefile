obj-m := gpio_sysfs.o
ARCH=arm
CROSS_COMPILE=arm-linux-gnueabihf-
KERNEL_DIR=/home/neko/Projects/BeagleBoneBlack_Linux_Device_Driver/linux_5.4/
HOST_KERNEL_DIR=/lib/modules/$(shell uname -r)/build/

all default: modules

modules modules_install help:
	make ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) -C $(KERNEL_DIR) M=$(shell pwd) $@
host:
	make -C $(HOST_KERNEL_DIR) M=$(shell pwd) modules
clean:
	make ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) -C $(KERNEL_DIR) M=$(shell pwd) clean
	make -C $(HOST_KERNEL_DIR) M=$(shell pwd) clean
