   
	
	16_Workqueue_in_own_workque


Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
To trigger interrupt read device file (sudo cat /dev/etx_device)
Now see the Dmesg (dmesg)
[ 2562.609446] Major = 246 Minor = 0
[ 2562.649362] Device Driver Insert…Done!!!
[ 2565.133204] Device File Opened…!!!
[ 2565.133225] Read function
[ 2565.133248] Shared IRQ: Interrupt Occurred
[ 2565.133267] Executing Workqueue Function
[ 2565.140284] Device File Closed…!!!

We can able to see the print “Shared IRQ: Interrupt Occurred“ and “Executing Workqueue Function“
Use “ps -aef” command to see our workqueue. You can able to see our workqueue which is “own_wq“
UID    PID   PPID     C     STIME     TTY       TIME            CMD

root   3516     2          0       21:35        ?        00:00:00   [own_wq]

Unload the module using sudo rmmod driver
 

Difference between Schedule_work and queue_work
If you want to use your own dedicated workqueue you should create workqueue using create_workqueue. In that time you need to put work on your workqueue by using queue_work function.
If you don’t want to create any own workqueue, you can use kernel global workqueue. In that condition, you can use schedule_work function to put your work to global workqueue.
