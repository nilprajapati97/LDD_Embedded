
		21_Tasklet_Dynamic_Method


Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
To trigger interrupt read device file (sudo cat /dev/etx_device)
Now see the Dmesg (dmesg)
linux@embetronicx-VirtualBox: dmesg

[12372.451624] Major = 246 Minor = 0
[12372.456927] Device Driver Insert…Done!!!
[12375.112089] Device File Opened…!!!
[12375.112109] Read function
[12375.112134] Shared IRQ: Interrupt Occurred
[12375.112139] Executing Tasklet Function : arg = 0
[12375.112147] Device File Closed…!!!
[12377.954952] Device Driver Remove…Done!!!

We can able to see the print “Shared IRQ: Interrupt Occurred“ and “Executing Tasklet Function : arg = 0“
Unload the module using sudo rmmod driver
