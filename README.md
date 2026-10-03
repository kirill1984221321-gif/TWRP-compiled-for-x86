# TWRP-compiled-for-x86
🐧 Custom x86 TWRP & Linux Kernel for QEMU/PC
Welcome to the repository dedicated to creating a custom bootable TWRP Recovery ISO for x86 (PC) powered by a custom-compiled Linux kernel from scratch.
"The birth of a digital child" — born from the idea of bypassing the limitations of prebuilt mobile ARM binaries to successfully run a native TWRP graphical environment inside QEMU on PC architecture.
🚀 Key Features
Custom Linux Kernel (5.4.y / i386): Compiled from scratch for PC architecture with essential drivers included (VirtIO, VESA, graphical output).
Custom init Script: A lightweight initialization script that bypasses Android-specific container constraints and directly launches the recovery graphical interface.
QEMU-Ready: Fully optimized for execution using the -cpu max flag alongside VirtIO mouse and keyboard emulation.
🛠 Tech Stack
Build OS: Ubuntu 24.04 (GitHub Codespaces)
Tools: make, gcc, cpio, bc, qemu-system-i386
Target Architecture: i386 / x86
📦 Quick Start in QEMU
To test and run the recovery image locally, execute the following command in your terminal: qemu-system-i386 \
    -m 2048 \
    -smp 2 \
    -cpu max \
    -vga std \
    -audio driver=none \
    -device virtio-mouse-pci \
    -device virtio-keyboard-pci \
    -boot d \
    -cdrom twrp_x86.iso \
    -serial stdio
    
