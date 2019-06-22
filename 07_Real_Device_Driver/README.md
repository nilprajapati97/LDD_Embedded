Compile the User Space Application
Use below line in terminal to compile the user space application.

gcc -o test_app test_app.c

Execution (Output)
As of now, we have driver.ko and test_app. Now we will see the output.

Load the driver using sudo insmod driver.ko
Run the application (sudo ./test_app)
*********************************
*******WWW.EmbeTronicX.com*******
****Please Enter the Option******
1. Write 
2. Read 
3. Exit 
*********************************

Select option 1 to write data to driver and write the string ( In this case i’m going to write “embetronicx” to driver.
1
Your Option = 1
Enter the string to write into driver :embetronicx
Data Writing ...Done!

****Please Enter the Option******
1. Write 
2. Read 
3. Exit 
*********************************

That “embetronicx” string got passed to the driver. And driver stored that string in the kernel space. That kernel space was allocated by kmalloc.
Now select the option 2 to read the data from the device driver.
2
Your Option = 2
Data Reading ...Done!

Data = embetronicx

See now, we got that string “embetronicx”.
Just see the below image for your clarification.



Note : Instead of using user space application, you can use echo and cat command. But one condition. If you are going to use echo and cat command, please allocate the kernel space memory in init function instead of open() function. I wont say why. You have to find the reason. If you found the reason please comment below. You can use dmesg to see the kernel log
