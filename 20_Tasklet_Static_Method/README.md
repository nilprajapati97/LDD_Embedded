
			20_Tasklet_Static_Method				


Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
To trigger interrupt read device file (sudo cat /dev/etx_device)
Now see the Dmesg (dmesg)
linux@embetronicx-VirtualBox: dmesg

[ 8592.698763] Major = 246 Minor = 0
[ 8592.703380] Device Driver Insert…Done!!!
[ 8601.716673] Device File Opened…!!!
[ 8601.716697] Read function
[ 8601.716727] Shared IRQ: Interrupt Occurred
[ 8601.716732] Executing Tasklet Function : arg = 1
[ 8601.716741] Device File Closed…!!!                                            [8603.916741] Device Driver Remove…Done!!!

We can able to see the print “Shared IRQ: Interrupt Occurred“ and “Executing Tasklet Function : arg = 1“
Unload the module using sudo rmmod driver
