

<h3> What is a BIOS? </h3>

<p> Basic Input Output System (BIOS) is a firmware that is pre-installed onto the motherboard. </p>
The Bios runs from the Read Only Memory (rom) which is configuered into the motherboard.
The Bios is completly independant of the operating system.


<h3> What does the BIOS DO? </h3>
The BIOS exceutes the Master Boot Record (MBR)

The Bios Performs a post test when the power button is pushed on a machine, and checks the folloiwng. 
- Hdd / SSD
- Ram
- I/O inputs



<h3> What is MBR? </h3>

Master boot record (MBR) loads/invokes the boot loader. Twhich can be lilo or grub.
Note Master boot record (MBR) is located on the first sector of the drive, it is aproximetly 525KB.


<h3> What is a GRUB? </h3>
Grand Unified Boot-loader (GRUB) is a boot loader.

<h3> What does GRUB do? </h3>
Grand Unified Boot-loader's main purpose is to load/execute the kernel into system ram 
Grub decides what operating to use, per user request. 
Grub is used on various operating systems
When utilizing Grub, you will be presented with a splash screen

NOTE: LILO was replaced by grub

<h3> What is LILO? </h3>
Linux Loader is a linux only boot-loader which was widly used untill it got replaced by GRUB
NOTE: LILO was replaced by grub

<h3> What is a Kernel? </h3>
Kernel is the core of the operating system.
Grub is what specifies which Kernel to choose depending on utilization.

The Compressed Kernel: 
/boot/vmlinuz

The Uncompressed kernel:
/boot/vmlinux


The Kernel loads Systemd.

Systemd manages linux process and mounts file systems

before Systemd, SysVinit was widely used 


<h3> What is LILO? </h3>
Linux Loader is a linux only boot-loader which was widly used untill it got replaced by GRUB
NOTE: LILO was replaced by grub






RAM: 
Random Access Memory


