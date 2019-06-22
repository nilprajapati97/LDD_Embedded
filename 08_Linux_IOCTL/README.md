

			08_Linux_IOCTL	


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

Opening Driver
Enter the Value to send

Enter the value to pass
23456
Writing Value to Driver
Reading Value from Driver
Value is 23456
Closing Driver

Now check the value using dmesg
Device File Opened...!!!
Value = 23456
Device File Closed...!!!

Our value 23456 was passed to the kernel and it was updated.
This is the simple example using ioctl in driver. If you want to send multiple arguments, put those variables into structure and pass the structure.
In our next tutorial we will see other userspace and kernel space communication methods.
