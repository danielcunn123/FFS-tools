<h1>Firmware RE</h1>

Multi-platform support, extend security research and development capabilities of modern firmware images & OTA (Over-the-Air) updates.

<br>

<h2>How it works</h2>

Extract FFS-tools (aarch64) into the root directory of the selected firmware filesystem '/'.

It is NOT RECOMMENDED to overwrite existing binaries, as this will run original executables from vendor for aditional testing - binaries may be customised from manufacture so its best to keep original binaries for application fuzzing and initial testing purposes. If things are not running smoothly, overwrite original binaries with included FFS binaries.

It is NOT RECOMMENED to deploy FFS-tools on real-world devices, stick with extracted firmware virtualised within isolated development enviroments.

<br>

There are three main reasons developers may find this project interesting:

* run system security audits on almost any device/platform - Including mobile platforms (such as Apple iOS & Android) + most router firmware.
* it is now **simple** to spawn a less-restrictive shell within Unix filesystems where FFS-tools is deployed with a single `chroot` command.
* for standalone application (testing/audit frameworks) to run smoother.

<br>

<h2>Getting Started</h2>

`wget https://github.com/danielcunn123/FFS-tools/releases/download/v0.2a-aarch64/FFS-tools.tar.gz`

`tar -xvf FFS-tools.tar.gz ~/ROOT/PATH/OF/FIRMWARE`

Fetch FFS-tools and extract into firmware filesystem root directory

<br>

`wget https://github.com/CISOfy/lynis/archive/refs/tags/3.0.8.tar.gz`

`tar -xvf 3.0.8.tar.gz ~/HOME/PATH/OF/FIRMWARE`


OPTIONAL - Fetch & extract security audit framework

<br>

`sudo chmod u+x -R PATH/TO/bin`

`sudo chroot . /bin/bash`

or

`sudo chroot . /bin/sh`


Enable 'execute' permissions to all binaries in firmware /bin and spawn either a BASH or SH shell

<br>

`uname -a`

- Linux rgfulw 5.15.0-56-generic #62-Ubuntu SMP Tue Nov 22 19:54:14 UTC 2022 **aarch64** GNU/Linux

Verify shell - Output should be similar to above plaintext.

<br>

<h2>What else</h2>

Uncompressed FFS-tools is 1.5GB size, compressed to 584MB for download.

One thing to note is the included tools are designed for 'aarch64', whereas not all firmware runs the same architecture - interestingly the toolset works with other platforms such as MIPS, PowerPC to name a few - Please open issues regarding lack-of-support or architecture missmatch so I can release a seprate patch for each architecture.

Of course there are going to be "missing files and directores". The intention of this project is to add only the bare essentials enough to just-work, allowing researchers to build a development enviroment and allow for expandability accross a broad range of firmware - as firmware functionality is often limited by-design, for good reason too.

I am not liable for anyone using this project for "hacking" purposes, or on intelectual property considered as "copyright material", therefore controlled by the copyright law - as it can be against the law to modify/reverse engineer firmware without explicit consent from the vendor unless otherwise stated within the user agreement policy for research and educational purposes. 

If things dont run smoothly this is where YOU troubleshoot the rest of the way. Happy hunting!!
