

						29_EXPORT_SYMBOL_in_Linux_Device_Driver	
				
	

Compiling and Testing Driver
Build the driver by using Makefile (sudo make)
After compiling, you can able to see the file named as “Module.symvers“. If you open that file, then our shared function and variable will be mentioned there.
0x1db7034a       etx_shared_func         /home/embetronicx/driver/driver1            EXPORT_SYMBOL
0x6dcb135c       etx_count                    /home/embetronicx/driver/driver1             EXPORT_SYMBOL

Load the driver 1 using sudo insmod driver1.ko(Driver 1 should be loaded first. If you try to load the Driver 2 first, then you will get an error like “insmod: ERROR: could not insert module driver2.ko: Unknown symbol in module“).
Load the driver 1 using sudo insmod driver2.ko
Now check the dmesg
[ 393.814900] Major = 246 Minor = 0
[ 393.818413] Device Driver 1 Insert…Done!!!
[ 397.620296] Major = 245 Minor = 0
[ 397.629002] Device Driver 2 Insert…Done!!!

Then do cat /proc/kallsyms | grep etx_shared_funcorcat /proc/kallsyms | grep etx_countto check whether our shared function and variable become the part of kernel’s symbol table or not.
Now we can read the driver by using sudo cat /dev/etx_device2
Now check the dmesg
[ 403.739998] Device File Opened…!!!
[ 403.740018] Shared function been called!!!
[ 403.740021] 1 time(s) shared function called!
[ 403.740023] Data Read : Done!
[ 403.740028] Device File Closed…!!!

Now we can see the print from shared function and variable count also.
Unload the module 2 using sudo rmmod driver2(Driver 2 should be unloaded first. If you unload the Driver 1 first, then you will get error like “rmmod: ERROR: Module driver1 is in use by: driver2“).
Unload the module 1 using sudo rmmod driver1

