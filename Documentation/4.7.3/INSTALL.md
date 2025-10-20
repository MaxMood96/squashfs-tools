# INSTALLING SQUASHFS-TOOLS 4.7.3

## Building squashfs tools

The squashfs-tools directory contains the source code for the Mksquashfs,
and Unsquashfs programs.  These can be compiled by typing "make".  This
will also create symbolic links sqfstar and sqfscat.

They can be installed, along with the symbolic links sqfstar and sqfscat,
to /usr/local/bin by typing "sudo make install".  The default install
location can be changed by editing the Makefile (INSTALL_PREFIX and
INSTALL_DIR).

### Compressors built by default

By default the Makefile is configured to build Mksquashfs and Unsquashfs
with support for all the compressors, which is GZIP, LZO, LZ4, XZ and ZSTD.
If you don't need some of these you can disable them by editing the Makefile.

### Default parallel reader threads

The Makefile is configured to build Mksquashfs to use four small reader threads
and four block reader threads by default.  The number of default reader threads
can be changed by editing the Makefile.

### Extended attribute support (XATTRs)

By default the Makefile is configured to build Mksquashfs and Unsquashfs
with extended attribute support.  Read the Makefile in squashfs-tools for
instructions on how to disable operating system support for extended attributes
if not supported by your system, or completely disable them if it is not needed.

## Kernel support

This release is for 2.6.29 and newer kernels.  Kernel patching is not necessary.

Extended attribute support requires 2.6.35 or newer kernels.  But
file systems with extended attributes can be mounted on 2.6.29 and
newer kernels (the extended attributes will be ignored with a warning).

LZO compression support requires 2.6.36 or newer kernels.

XZ compression support requires 2.6.38 or newer kernels.

LZ4 compression support requires 3.11 or newer kernels.

ZSTD compression support requires 4.14 or newer kernels.
