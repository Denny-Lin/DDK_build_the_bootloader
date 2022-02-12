# DDK_build_the_bootloader
Use the cross compiler to build the bootloader (MLO + u-boot, MLO + barebox).

Host machine <br/>
uname -a <br/>
Linux ubuntu 5.13.0-28-generic #31~20.04.1-Ubuntu SMP Wed Jan 19 14:08:10 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux 
&nbsp;

Target machine <br/>
arm &nbsp;

# Download the source files of the Crosstool-NG
git clone git://git.denx.de/u-boot.git <br/>
cd u-boot &nbsp;

git checkout v2015.07 &nbsp;

```C
Note: switching to 'v2015.07'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 33711bdd4a Prepare v2015.07
```

# Create the .config
make CROSS_COMPILE=arm-cortex_a8-linux-gnueabi- am335x_boneblack_defconfig &nbsp;

## Issue
Can't find default configuration "arch/../configs/am335x_boneblack_defconfig"! <br/>
git checkout v2015.07 &nbsp;

# Build the bootloader
make CROSS_COMPILE=arm-cortex_a8-linux-gnueabi-

## Issue
fatal error: linux/compiler-gcc11.h: No such file or directory <br/>
cd /home/denny/Desktop/u-boot <br/>
cp ./include/linux/compiler-gcc5.h ./include/linux/compiler-gcc11.h &nbsp;

# Image path
cd /home/denny/Desktop/u-boot <br/>
ls MLO u-boot* <br/>
MLO  u-boot  u-boot.bin  u-boot.cfg  u-boot.img  u-boot.lds  u-boot.map  u-boot.srec &nbsp;


