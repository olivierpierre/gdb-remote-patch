# gdb-remote-patch
Fix the "gdb remote packet reply is too long" issue on recent GDB versions.

There is a classical issue when using DGB remote debugging feature, for example on embedded systems or when debugging Linux with Qemu: after connecting to the target, the first interrupt in GDB yields this error message: "gdb remote packet reply is too long".

There is a patch available here: http://www.cygwin.com/ml/gdb-patches/2012-03/msg00116.html, that does not work with recent versions of GDB. It has been slightly modified here.

## Usage
Place the patch at the root of GDB sources (this has been tested with GDB 7.11), then do:

```shell
patch -p1 < gdb-remote.patch
```
