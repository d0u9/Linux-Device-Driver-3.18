ifneq ($(KERNELRELEASE),)
    ccflags-y := -std=gnu99 -DENABLE_DEBUG
    short_ioport-objs := main.o
    obj-m := short_ioport.o
else
    KERNELDIR ?= /lib/modules/$(shell uname -r)/build
    PWD := $(shell pwd)

.PHONY: clean
modules:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules
endif

.PHONY: clean
clean:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) clean

CFLAGS_main.o := -DDEBUG
