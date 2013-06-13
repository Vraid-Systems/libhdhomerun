BUILD libhdhomerun and hdhomerun_config
============
For those of you using this like normal people, simply a `make` will suffice.
But ... where is the fun in that?

setup CROSS_COMPILE env
------------
I attempted to roll a cross-compile environment in Cygwin for several hours
and gave up. Everything was so much easier on a Debian 7 VM.

1. http://www.mentor.com/embedded-software/sourcery-tools/sourcery-codebench/editions/lite-edition/arm-gnu-linux
2. Run the installer. Something like: `./arm-2013.05-24-arm-none-linux-gnueabi.bin`
3. In `~/.profile`, stick in something like:
`PATH="/root/CodeSourcery/Sourcery_CodeBench_Lite_for_ARM_GNU_Linux/bin:$PATH"`
... or wherever you pointed the installer to.

ARM A9 Cortex example
------------
Rocking this for the [XIOS DS Media Play](http://www.pivosgroup.com/xios.html)
- `make clean`
- `make ARCH=arm CROSS_COMPILE=arm-none-linux-gnueabi- CFLAGS="-march=armv7-a -mcpu=cortex-a9 -marm -mlittle-endian -mglibc" all`
