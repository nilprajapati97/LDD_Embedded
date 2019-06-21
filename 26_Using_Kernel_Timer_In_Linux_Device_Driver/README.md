

	26_Using_Kernel_Timer_In_Linux_Device_Driver

	

Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
Now see the Dmesg (dmesg)
linux@embetronicx-VirtualBox: dmesg

[ 2253.635127] Device Driver Insert…Done!!!
[ 2258.642048] Timer Callback function Called [0]
[ 2263.647050] Timer Callback function Called [1]
[ 2268.652684] Timer Callback function Called [2]
[ 2273.658274] Timer Callback function Called [3]
[ 2278.663885] Timer Callback function Called [4]
[ 2283.668997] Timer Callback function Called [5]
[ 2288.675109] Timer Callback function Called [6]
[ 2293.680160] Timer Callback function Called [7]
[ 2298.685771] Timer Callback function Called [8]
[ 2303.691392] Timer Callback function Called [9]
[ 2308.697013] Timer Callback function Called [10]
[ 2313.702033] Timer Callback function Called [11]
[ 2318.707772] Timer Callback function Called [12]

See the timestamp. That callback function is executing every 5 seconds.
Unload the module using sudo rmmod driver
Points to remember
This timer callback function will be executed from interrupt context. If you want to check that, you can use function in_ interrupt( ), which takes no parameters and returns nonzero if the processor is currently running in interrupt context, either hardware interrupt or software interrupt. Since it is running in interrupt context, user cannot perform some actions inside the callback function mentioned below.

Go to sleep or relinquish the processor
Acquire a mutex
Perform time-consuming tasks
Access user space virtual memory
