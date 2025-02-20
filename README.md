# SoC Emulation and System Design
This repo is created as a teaching tool to get familiar with SoC design. More specifically, how an embedded system is designed and how different components interact. The purpose of this exercise is to close the gap between software developers that work at the "high-level" of programming with the low-level hardware design. For this, the goal is to design a simple SoC from start to finish and run software on it. This README will link to the individual steps as we go along assuming some knowledge but trying to be verbose about the thought process as we build up our SoC and our development environment.

# Steps to build an SoC
## 1. Obtain our emulation software, QEMU
Eventually, it would be nice to print this design, but we are very far away from that. To start, emulating our device in software seems the most achievable task before delving into the world of FPGAs and digital design. QEMU is an open-source tool that allows emulating systems in software and is used in the embedded systems industry. For those reason, we will start with it. Follow the [QEMU](1-qemu-setup.md) getting started to get QEMU development environment and run some sanity tests to make sure it is working for the next steps.

## 2. Boot Linux on an ARM64 machine in QEMU
Now that we have QEMU setup, we can use it to run out own machine. The simplest thing we can do is to boot a Linux kernel on an ARM64 machine from QEMU. We'll walk through the steps of obtaining and building the Linux kernel for our target device, preparing the necessary components for the machine and then booting it through QEMU. Follow the [First-Linux-Boot](2-first-linux-boot.md) for these steps.
