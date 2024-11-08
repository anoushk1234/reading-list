### Part 1
Cross compile to generic target so grub can boot our OS.

- Theres no stack, virtual memory so we need to setup global variables in asm,
- The vars will contain multiboot headers that the bootloaders will look for and identity our kernal as bootable.
- Freestanding env doenst include std c libs unlike hosted environment, the compiler includes certain lib necessary for os dev even in freestanding.

    boot.s - kernel entry point that sets up the processor environment
    kernel.c - your actual kernel routines
    linker.ld - for linking the above files
