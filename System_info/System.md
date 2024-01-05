

What is BIOS?

BIOS: Basic Input Output System is firmware that is pre-installed onto the motherboard.
The Bios runs from the Read Only Memory (rom) which is configuered into the motherboard.
The Bios is completly independant of the operating system.
The BIOS exceutes the Master Boot Record (MBR)

The Bios Performs a post test when the power button is pressed on machine, to check the following
- Hdd / SSD
- Ram
- I/O inputs



What is MBR?

MBR:
Master boot record loads/invokes the boot loader, which can be lilo or grub.
Note Master boot record (MBR) is located on the first sector of the drive, it is aproximetly 525KB.


What is GRUB?
Grand Unified Boot-loader is a boot loader.

What does GRUB do?
Grand Unified Boot-loader's main purpose is to load/execute the kernel into system ram 
Grub decides what operating to use, per user request. 
Grub is used on various operating systems
When utilizing Grub, you will be presented with a splash screen

NOTE: LILO was replaced by grub


What is a Kernel?
Kernel is the core of the operating system.
Grub is what specifies which Kernel to choose depending on utilization.


What is LILO?
Linux Loader is a linux only boot-loader which was widly used untill it got replaced by GRUB
NOTE: LILO was replaced by grub



After Kerenl is loaded, SystemD will be aviable to use



Compressed Kernel: 
/boot/vmlinuz


Uncompressed kernel:
/boot/vmlinux


The Kernel loads Systemd.

Systemd manages linux process and mounts file systems

before Systemd, SysVinit was widely used 




RAM: 
Random Access Memory


