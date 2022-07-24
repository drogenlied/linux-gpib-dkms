# DKMS package for the linux-gpib kernel driver
## Prerequisites
At least the Debian packages `devscripts`, `dkms`, `subversion`, `git`

## Build
Check out the linux-gpib source:

`svn checkout https://svn.code.sf.net/p/linux-gpib/code/trunk linux-gpib`

Copy the `debian` folder from this repository into `linux-gpib/linux-gpib-kernel/`

In the `linux-gpib-kernel` directory, run `debuild -i -us -uc -b`
Install any packages that `debuild` complains about. If the build goes smoothly, you should find 
`gpib-dkms_X.X.X+svnXXXX_all.deb` in the `linux-gpib` directory.

## Install
Install with `dpkg`, if building the kernel modules fails during package installation, 
check that you have the correct kernel souce, compiler and other build tools installed
to successfully build a kernel module.

Tested on with linux-gpib 4.3.5, Kernel 5.18, may or may not work on future versions.
