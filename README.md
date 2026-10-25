KuiperBSD Source:
---------------
This is the top level of the KuiperBSD source directory.

KuiperBSD is a fork of FreeBSD operating system and is an attempt to modernize, improve and optimize BSD without breaking any of it's current functionality

It's nameed after the KuiperBelt (the icy frontier surrounding Pluto , The 9th planet).

## Goals
| Subsystem | KuiperBSD Goal |
| :--- | :--- |
| Per-Process Namespaces | Enable unprivileged, mutable per-process VFS views and union directory overlays via `rfork(RFNAMEG)` without altering the global mount table for standard processes. |
| Synthetic `/net` Stack | Expose the kernel network stack as a Plan 9-style `/net` file hierarchy (`/net/tcp/clone`, `ctl`, `data`) backed directly by native BSD kernel sockets and `kqueue`. |
| In-Kernel 9P (`StyxVFS`) | Provide a lightweight synthetic filesystem layer to replace opaque `ioctl()` and `sysctl()` interfaces with clean, network-transparent 9P file trees. |
| Hardware Telemetry (`/hw`) | Map open hardware controllers (starting with Raspberry Pi) into readable and writable synthetic files (`/hw/framework/battery/ctl`). |
| Zero-Breakage ABI | Maintain 100% FreeBSD KBI/ABI and POSIX compatibility so existing binaries, `pkg` repositories, and Jails run unmodified at native speed. |


For copyright information, please see [the file COPYRIGHT](COPYRIGHT) in this directory.
Additional copyright information also exists for some sources in this tree - please see the specific source directories for more information.

The Makefile in this directory supports a number of targets for building components (or all) of the FreeBSD source tree.
See build(7), config(8), [FreeBSD handbook on building userland](https://docs.freebsd.org/en/books/handbook/cutting-edge/#makeworld), and [Handbook for kernels](https://docs.freebsd.org/en/books/handbook/kernelconfig/) for more information, including setting make(1) variables.

For information on the CPU architectures and platforms supported by FreeBSD, see the [FreeBSD
website's Platforms page](https://www.freebsd.org/platforms/).

For official FreeBSD bootable images, see the [release page](https://download.freebsd.org/ftp/releases/ISO-IMAGES/).

Source Roadmap:
---------------
| Directory | Description |
| --------- | ----------- |
| bin | System/user commands. |
| cddl | Source code for third-party software under the Common Development and Distribution License. |
| contrib | Source code for third-party software. |
| crypto | Source code for cryptographic libraries and commands (see [crypto/README](crypto/README)). |
| etc | Template files for /etc. |
| include | System include files. |
| kerberos5 | Build system for Kerberos 5 (Heimdal). |
| krb5 | Build system for Kerberos 5 (MIT). |
| lib | System libraries. |
| libexec | System commands intended to be executed by other commands or daemons. |
| packages | Base system packages. |
| release | Makefiles and scripts used for building releases and VM images. |
| rescue | Build system for statically linked /rescue commands. |
| sbin | System commands. |
| secure | Build system for cryptographic libraries and commands (excluding Kerberos). |
| share | Shared resources. |
| stand | Boot loader sources. |
| sys | Kernel sources (see [sys/README.md](sys/README.md)). |
| targets | Support for experimental `DIRDEPS_BUILD` |
| tests | Tests which can be run by Kyua.  See [tests/README](tests/README) for additional information. |
| tools | Ancillary utilities and tests (not included in the build). |
| usr.bin | User commands. |
| usr.sbin | System administration commands. |

For information on synchronizing your source tree with one or more of the FreeBSD Project's development branches, please see [FreeBSD Handbook](https://docs.freebsd.org/en/books/handbook/cutting-edge/#current-stable).
