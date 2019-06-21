
	15_Workque_in_linux_Dynamic_Method


Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
To trigger interrupt read device file (sudo cat /dev/etx_device)
Now see the Dmesg (dmesg)
linux@embetronicx-VirtualBox: dmesg

[11213.943071] Major = 246 Minor = 0
[11213.945181] Device Driver Insert…Done!!!
[11217.255727] Device File Opened…!!!
[11217.255747] Read function
[11217.255783] Shared IRQ: Interrupt Occurred
[11217.255845] Executing Workqueue Function
[11217.255860] Device File Closed…!!!

We can able to see the print “Shared IRQ: Interrupt Occurred“ and “Executing Workqueue Function“
Unload the module using sudo rmmod driver
