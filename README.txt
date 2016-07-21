Please use the following steps to integrate vl53L0 driver into your kernel:

- copy the include and drivers folders into the root of kernel source:
	cp -r drivers <KERNEL_SRC_ROOT>/

- edit input Kconfig (drivers/input/misc/Kconfig) to include STMVL53L0 config
  adding the following lines:

config STMVL53L0
    tristate "STM VL53L0 Proximity support"
    depends on I2C=y
    default y
    help
      Say Y here if you want to use STMicroelectronics's proximity sensor
      through I2C interface.

      To compile this driver as a module, choose M here: the
      module will be called stmvl53l0.


- edit input Makefile (drivers/input/misc/Makefile) adding the following line:
	obj-y += vl53L0/


To enable this driver you have to make the needed changes in the board file or
into platform device tree.
	 

