# linux-kernel-mod-tutorial-fix
Fix a problem with the chardev.c Linux kernel mod at http://www.tldp.org/LDP/lkmpg/2.6/html/x569.html

chardev.c at http://www.tldp.org/LDP/lkmpg/2.6/html/x569.html failed to compile on Linux kernel 3.13.0-32-generic 
with error: void value not ignored as it ought to be
  int ret = unregister_chrdev(Major, DEVICE_NAME);
  
This was due to unregister_chrdev being changed to type void in later kernels. 
Changed to void type in the example and it now compiles properly.
Full corrected example is listed here.



Caution: this file contains a Linux kernel mod. Kernel mods can result in catastrophic consequences if not implemented properly. Procced with extreme caution.
