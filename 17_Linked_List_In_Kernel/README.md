	17_Linked_List_In_Kernel  

Building and Testing Driver
Build the driver by using Makefile (sudo make)
Load the driver using sudo insmod driver.ko
sudo su
To trigger interrupt read device file (cat /dev/etx_device)
Now see the Dmesg (dmesg)
[ 5310.125001] Major = 246 Minor = 0 n
[ 5310.133127] Device Driver Insert…Done!!!
[ 5346.839872] Device File Opened…!!!
[ 5346.839950] Read function
[ 5346.839954] Total Nodes = 0
[ 5346.839982] Device File Closed…!!!

By this time there is no nodes available.
So now write the value to driver using echo 10 > /dev/etx_device
By this time, One node has been added to the linked list.
To test that read the device file using cat /dev/etx_device
Now see the Dmesg (dmesg)
[ 5346.839982] Device File Closed…!!!
[ 5472.408239] Device File Opened…!!!
[ 5472.408266] Write Function
[ 5472.408293] Shared IRQ: Interrupt Occurred
[ 5472.408309] Device File Closed…!!!
[ 5472.409037] Executing Workqueue Function
[ 5551.996018] Device File Opened…!!!
[ 5551.996040] Read function
[ 5551.996044] Node 0 data = 10
[ 5551.996046] Total Nodes = 1
[ 5551.996052] Device File Closed…!!!

Our value has added to the list.
You can also write many times to create and add the node to linked list
Unload the module using rmmod driver
