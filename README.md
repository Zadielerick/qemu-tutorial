# QEMU Tutorial
A small example of launching qemu, running a simple ARM or RISC-V based device and adding a custom peripheral.

## Pre-Setup
My setup is a Debian Bookwork Linux PC.

## Installing QEMU
Following the official [QEMU download page](https://www.qemu.org/download/), clone the sources so we can build qemu from scratch. It's probably not necessary but it would be good practice to get familiar with building it and having all the dependencies downloaded as well.

### Step 1: Download QEMU dependencies and suggested utils 
#### (15 mins)
To start, actually follow the instructions on the [QEMU wiki](https://wiki.qemu.org/Hosts/Linux) for building for Linux hosts. I made a quick bash script and copied and pasted all their 'apt install' commands since it was tedious to do one by one.

### Step 2: Build QEMU and run simple sanity test
#### (20+ mins, depending on how good you are at solving missing dependencies and your machine build speed)
Next, build the simple test described in the wiki. I'll follow the recommended out-of-tree build (build not directly in the root directory of the repo). I'll also checkout a stable branch just to not mess with the bleeding-edge issues I could face.

```
cd qemu; git checkout stable-9.2; mkdir bin/debug/native; cd bin/debug/native; ../../../configure --enable-debug; make; cd -
```
Note: Ran into an issue about missing a python pacakge, installed `python3-venv` based on the error message (apt install python3-venv)
Note: Ran into an issue about missing `flex` and `bison`, also installed them (apt install flex bison)

Then ran make full speed: make -j
Note: If that crashes your machine then just set to the actual thread count, something safe like make -j4

Finally, ran the simple test command, had to modify it as it seemed to change from the instructions: `./bin/debug/native/qemu-system-x86_64 -L pc-bios`
