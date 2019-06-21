
		25_Sending_Signal_from_Linux_Device_Driver_to_User_Space


Building Driver and Application
Build the driver by using Makefile (sudo make)
Use below line in terminal to compile the user space application.

	gcc -o test_app test_app.c

Execution (Output)
As of now, we have driver.ko and test_app. Now we will see the output.

Load the driver using sudo insmod driver.ko
Run the application (sudo ./test_app)
*********************************
*******WWW.EmbeTronicX.com*******
*********************************
Installed signal handler for SIGETX = 44

Opening Driver
Registering application …Done!!!
Waiting for signal…

This application will be waiting for signal
To send the signal from driver to app, we need to trigger the interrupt by reading the driver (sudo cat /dev/etx_device).
Now see the Dmesg (dmesg)
Major = 246 Minor = 0
Device Driver Insert…Done!!!
Device File Opened…!!!
REG_CURRENT_TASK
Device File Opened…!!!
Read Function
Shared IRQ: Interrupt Occurred
Sending signal to app
Device File Closed…!!!

As per the print, driver has send the signal. Now check the app.
Received signal from kernel : Value = 1

So application also got the signal.
Close the application by pressing CTRL+C
Unload the module using sudo rmmod driver
