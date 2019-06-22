
				Linux Device Driver Tutorial Part 10 – WaitQueue in Linux


Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
Then Check the Dmesg
Major = 246 Minor = 0
Thread Created successfully
Device Driver Insert…Done!!!
Waiting For Event…

So that thread is waiting for the event. Now we will send the event by reading the driver using sudo cat /dev/etx_device
Now check the dmesg
Device File Opened…!!!
Read Function
Event Came From Read Function – 1
Waiting For Event…
Device File Closed…!!!

We send the wake up from read function, So it will print the read count and then again it will sleep. Now send the event from exit function by sudo rmmod driver
Event Came From Exit Function
Device Driver Remove…Done!!!

Now the condition was 2. So it will return from the thread and remove the driver.
