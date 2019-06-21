

		27_Using_High_Resolution_Timer_In_Linux_Device	


Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
Now see the Dmesg (dmesg)
linux@embetronicx-VirtualBox: dmesg

[ 2643.773119] Device Driver Insert…Done!!!
[ 2648.773546] Timer Callback function Called [0]
[ 2653.773609] Timer Callback function Called [1]
[ 2658.774170] Timer Callback function Called [2]
[ 2663.773271] Timer Callback function Called [3]
[ 2668.773388] Timer Callback function Called [4]

See the timestamp. That callback function is executing every 5 seconds.
Unload the module using sudo rmmod driver
Points to remember
This timer callback function will be executed from interrupt context. If you want to check that, you can use function in_ interrupt( ), which takes no parameters and returns nonzero if the processor is currently running in interrupt context, either hardware interrupt or software interrupt. Since it is running in interrupt context, user cannot perform some actions inside the callback function mentioned below.

Go to sleep or relinquish the processor
Acquire a mutex
Perform time-consuming tasks
success user space virtual memory
