--------->>>   13 interrupt Example Linux Kernel  <<<-------------------
**************************************************************************



Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
To trigger interrupt read device file (sudo cat /dev/etx_device)
Now see the Dmesg (dmesg)
linux@embetronicx-VirtualBox: dmesg

[19743.366386] Major = 246 Minor = 0
[19743.370707] Device Driver Insert…Done!!!
[19745.580487] Device File Opened…!!!
[19745.580507] Read function
[19745.580531] Shared IRQ: Interrupt Occurred
[19745.580540] Device File Closed…!!!

We can able to see the print “Shared IRQ: Interrupt Occurred“
Unload the module using sudo rmmod driver
This is the simple example using Interrupts in device driver. This is just a basic. You can also try using hardware. I hope this might helped you.
