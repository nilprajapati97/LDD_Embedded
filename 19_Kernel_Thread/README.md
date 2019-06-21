

			19_Kernel_Thread	



Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
Then Check the Dmesg
Major = 246 Minor = 0
Device Driver Insert…Done!!!
In EmbeTronicX Thread Function 0
In EmbeTronicX Thread Function 1
In EmbeTronicX Thread Function 2
In EmbeTronicX Thread Function 3

So our thread is running now.
removn driver using sudo rmmod driver to stop the thread.
