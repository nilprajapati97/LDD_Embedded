Linux Device Driver Tutorial Part 9 – Procfs in Linux 

Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
Check our procfs entry using ls in procfs directory
linux@embetronicx-VirtualBox:ls /proc/

 filesystems      iomem      kallsyms      modules    partitions

Now our procfs entry is there under /proc directory.
Now you can read procfs variable using cat.
linux@embetronicx-VirtualBox:  cat /proc/etx_proc

try_proc_array

We initialized the etx_array with “try_proc_array”. That’s why we got “try_proc_array”.
Now do proc write using echo command and check using cat.
linux@embetronicx-VirtualBox: echo "device driver proc" > /proc/etx_proc

linux@embetronicx-VirtualBox:  cat /proc/etx_proc

device driver proc

We got the same string which was passed to the driver using procfs.
This is the simple example using procfs in device driver. This is just a basic. I hope this might helped you.
