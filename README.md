This is my summary of the Linux Command line and Shell scripting Bible, by Richard Blum and Christine Bresnahan. This book is considered a great introduction to linux adminstartion with practical exercises as found in the real-world projects.
Contributions: Issues, comments and pull requests are super welcome 😃
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->
# Table of Contents
- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
- [Chapter 1. Starting with Linux Shells](#chapter-1-starting-with-linux-shells)
- [Chapter 2. Getting to the Shell](#chapter-2-getting-to-the-shell)
<!-- /TOC -->

# Introduction
Welcome to the fourth edition of Linux Command Line and Shell Scripting Bible. Like all books in the Bible series, you can expect to find both hands on tutorials and real-world information, as well as reference and background information that provides a context for what you are learning. This book is a fairly comprehensive resource on the Linux command line and shell commands. By the time you have completed Linux Command Line and Shell Scripting Bible, you will be well prepared to write your own shell scripts that can automate practically any task on your Linux system.


# Chapter 1. Starting with Linux Shells
- Before we can dive into working with the Linux command line and shells, it's a good idea to first understand what Linux is, where it came from, and how it works.
- Four main parts make up a Linux system
	- The Linux kernel
	- The GNU utilities
	- A graphical desktop environment
	- Application software
- The Linux Kernel
	- The kernel controls all the hardware and software on the computer system, allocating hardware when necessary and executing software when required.
	- The kernel is primarily responsible for four main functions:
		- System memory management
			- The Linux Kernel manages the virtual and physical memory be swapping in and out memory pages.
		- Software program management
			- The Linux operating system calls a running program a process.
			- A process can run in the foreground, displaying output on a display, or it can run in the background, behind the scenes.
			- The kernel controls how the Linux system manages all the processes running on the system.
			- The kernel creates the first process, called the init process, to start all other processes on the system. When the kernel starts, it loads the init process into virtual memory.
			- The most popular init implementations are
				- SysVinit
				- Systemd
		- Hardware management
			- Any device that the Linux system must communicate with needs driver code inserted inside the kernel code.
			- The driver code allows the kernel to pass data back and forth to the device, acting as an intermediary between applications and the hardware.
				- Drivers compiled in the kernel
				- Driver modules added to the kernel
			- The Linux system identifies hardware devices as special files, called device files.
				- Character: are for devices that can handle data only one character at a time. For example, modems and terminals.
				- Block: are for devices that can handle data in large blocks at a time, such as disk drives.
				- Network: are used for devices that use packets to send and receive data. This includes network cards and a special loopback device that allows the Linux system to communicate with itself using common network programming protocols.
		- Filesystem management
			- Linux kernel can support different types of filesystems to read and write data to and from hard drives.
			- The Linux kernel interfaces with each filesystem using the Virtual File System (VFS). 
			- This provides a standard interface for the kernel to communicate with any type of filesystem. 
			- VFS caches information in memory as each filesystem is mounted and used.
			- Linux Filesystems
				- ext: Linux extended filesystem — the original Linux filesystem
				- ext2: Second extended filesystem; provided advanced features over ext
				- ext3: Third extended filesystem; supports journaling
				- ext4: Fourth extended filesystem; supports advanced journaling
				- btrfs: A newer, high-performance filesystem that supports journaling and large files
				- exfat: The extended Windows filesystem, used mainly for SD cards and USB sticks
				- hpfs: OS/2 high-performance filesystem
				- jfs: IBM's journaling filesystem
				- iso9660: ISO 9660 filesystem (CD-ROMs)
				- minix: MINIX filesystem
				- msdos: Microsoft FAT16
				- ncp: NetWare filesystem
				- nfs: Network File System
				- ntfs: Support for Microsoft NT filesystem
				- proc: Access to system information
				- smb: Samba SMB filesystem for network access
				- sysv: Older Unix filesystem
				- ufs: BSD filesystem
				- umsdos: Unix-like filesystem that resides on top of msdos
				- vfat: Windows 95 filesystem (FAT32)
				- XFS: High-performance 64-bit journaling filesystem
- The GNU utilities
	- Besides having a kernel to control hardware devices, a computer operating system needs utilities to perform standard functions, such as controlling files and programs.
	- The GNU coreutils package consists of three parts:
		- Utilities for handling files
		- Utilities for manipulating text
		- Utilities for managing processes
	- The GNU/Linux shell is a special interactive utility. It provides a way for users to start programs, manage files on the filesystem, and manage processes running on the Linux system.
	- Linux Shells:
		- ash
		- korn
		- bash
		- tcsh
		- zsh
- The Linux desktop environment
	- The X Window software
	- The KDE Plasma desktop
	- The GNOME desktop
- A complete Linux system package is called a distribution.
	- Full-core Linux distributions
		- Slackware
		- Red Hat Enterprise
		- Gentoo
		- openSUSE
		- Debian
	- Specialized distributions
		- Fedora
		- Ubuntu
		- MX Linux
		- Linux Mint
		- Puppy Linux

# Chapter 2. Getting to the Shell
- Before the days of graphical desktops, the only way to interact with a Unix system was through a text command-line interface (CLI) provided by the shell.
- One way to get to a CLI is to access the Linux system via text mode. This provides nothing more than a simple shell CLI on the monitor, just like the days before graphical desktops.
- When the Linux system starts, it automatically creates several virtual consoles.
	- A virtual console is a terminal session that runs in Linux system memory.
- A terminal emulation package simulates working on a console terminal but within a desktop graphical window.
- Graphical Interface Elements:
	- Client: An application that requests graphical services.
	- Display Server: Element that manages the display (screen) and the input devices (keyboard, mouse, touch screen).
	- Window Manager: Element that adds borders to windows and provides features to move and manage windows.
	- Widgets Library: Element that adds menus and appearance items for desktop environment clients.
- tty stands for teletypewriter. Teletypewriter is an old term, indicating a machine used for sending messages.
- Within the Linux virtual console, you do not have the ability to run any graphical programs.
- GNOME Terminal is the GNOME Shell desktop environment's default terminal emulator.
	- Used by: Red Hat Enterprise Linux (RHEL), CentOS, and Ubuntu.
