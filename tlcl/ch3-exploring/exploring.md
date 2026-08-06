# Exploring the System

## `ls`

`ls` - basic
`ls /usr` - list /usr directory
`ls ~ /usr` - list home and /usr directory

`ls -l` - long form list

## Options and Arguments

`command -options arguments`

`ls -lt`  - long list and sorts by time
`ls -lt --reverse`  - long list, time sort, reversed

|Option|Long|Description|
|---|---|---|
| -a | --all | List all files, even those with names that begin with a period, which are normally not listed (that is, hidden).|| -A | --almost-all | Like the -a option above except it does not list . (current directory) and .. (parent directory).|
|-d | --directory| Ordinarily, if a directory is specified, ls will list the contents of the directory, not the directory itself. Use this option in conjunction with the -l option to see details about the directory rather than its contents. |
|-F | --classify | This option will append an indicator character to the end of each listed name. For example, a forward slash (/) if the name is a directory. |
|-h | --human-readable | In long format listings, display file sizes in human readable format rather than in bytes.|
|-L  |  | Display results in long format|
| -r | --reverse | Display the results in reverse order. Normally, ls displays its results in ascending alphabetical order.|
| -S |  | Sort results by file size.|
|-t |  | Sort by modification time.|


## Long Format

`ls -l` - long format

-rw-r--r-- 1 root root 32059 2017-04-03 11:05 oo-cd-cover.odf

|Field | Meaning|
|---|---|
|-rw-r--r--| Access rights to the file. The first character indicates the type of file. Among the different types, a leading dash means a regular file, while a “d” indicates a directory. The next three characters are the access rights for the file's owner, the next three are for members of the file's group, and the final three are for everyone else. Chapter 9 "Permissions" discusses the full meaning of this in more detail.|
|1 | File's number of hard links. See the sections "Symbolic Links" and "Hard Links" later in this chapter.|
|root|The username of the file's owner.|
|root|The name of the group that owns the file.|
|32059|Size of the file in bytes.|
|2017-04-03 11:05|Date and time of the file's last modification.|
|oo-cd-cover.odf|Name of the file.|

## File Type

Determine file type

`file <filename>`

```bash
$ file avatar.png
avatar.png: PNG image data, 1080 x 1080, 8-bit/color RGB, non-interlaced
```

## View File Contents

`less <filename>`

Command to view text files.

|Command|Action|
|---|---|
|Page Up or b|Scroll back one page|
|Page Down or space|Scroll forward one page|
|Up arrow|Scroll up one line|
|Down arrow|Scroll down one line|
|G|Move to the end of the text file|
|1G or g|Move to the beginning of the text file|
|/characters|Search forward to the next occurrence of characters|
|n|Search for the next occurrence of the previous search|
|h|Display help screen|
|q|Quit less|

## File System

|Directory|Comments|
|---|---|
|/|The root directory. Where everything begins.|
|/bin|Contains binaries (programs) that must be present for the system to boot and run. Note that modern Linux distributions have deprecated /bin in favor of /usr/bin(see below).|
|/boot|Contains the Linux kernel, initial RAM disk image (for drivers needed at boot time), and the boot loader. Interesting files:<br /> ● /boot/grub/grub.cfg or menu.lst, which is used to configure the boot loader.<br />● /boot/vmlinuz (or something similar), the Linux kernel|
|/dev|This is a special directory that contains device nodes. “Everything is a file” also applies to devices. Here is where the kernel maintains a list of all the devices it understands.|
|/etc|The /etc directory contains all of the system-wide configuration files. It also contains a collection of shell scripts that start each of the system services at boot time. Everything in this directory should be readable text.<br /><br />Interesting files: While everything in /etc is interesting, here are some all-time favorites:<br />● /etc/crontab, on systems that use the cron program, this file defines when automated jobs will run.<br />● /etc/fstab, a table of storage devices and their associated mount points.<br />● /etc/passwd, a list of the user accounts.|
|/home|In normal configurations, each user is given a directory in /home. Ordinary users can only write files in their home directories. This limitation protects the system from errant user activity.|
|/lib|Contains shared library files used by the core system programs. These are similar to dynamic link libraries (DLLs) in Windows. This directory has been deprecated in modern distributions in favor of /usr/lib.
|/lost+found|Each formatted partition or device using a Linux file system, such as ext4, will have this directory. It is used in the case of a partial recovery from a file system corruption event. Unless something really bad has happened to our system, this directory will remain empty.|
|/media|On modern Linux systems the /media directory will contain the mount points for removable media such as USB drives, CD-ROMs, etc. that are mounted automatically at insertion.|
|/mnt|On older Linux systems, the /mnt directory contains mount points for devices that have been mounted manually.|
|/opt|The /opt directory is used to install “optional” software. This is mainly used to hold commercial software products that might be installed on the system.|
|/proc|The /proc directory is special. It's not a real file system in the sense of files stored on the hard drive. Rather, it is a virtual file system maintained by the Linux kernel. The “files” it contains are peepholes into the kernel itself. The files are readable and will give us a picture of how the kernel sees the computer. Browsing this directory can reveal many details about the computer’s hardware.|
|/root|This is the home directory for the root account.|
|/run|This is a modern replacement for the traditional /tmp directory (see below). Unlike /tmp, the /run directory is mounted using the tempfs file system type which stores its contents in memory rather than on a physical disk.|
|/sbin|This directory contains “system” binaries. These are programs that perform vital system tasks that are generally reserved for the superuser. Note that modern Linux distributions have deprecated /sbin in favor of /usr/sbin (see below).|
|/sys|The /sys directory contains information about devices that have been detected by the kernel. This is much like the contents of the /dev directory but is more detailed including such things actual hardware addresses.|
|/tmp|The /tmp directory is intended for the storage of temporary, transient files created by various programs. Some distributions empty this directory each time the system is rebooted.|
|/usr|The /usr directory tree is likely the largest one on a Linux system. It contains all the programs and support files used by regular users.|
|/usr/bin|/usr/bin contains the executable programs installed by the Linux distribution. It is not uncommon for this directory to hold thousands of programs.|
|/usr/lib|The shared libraries for the programs in /usr/bin.|
|/usr/local|The /usr/local tree is where programs that are not included with the distribution but are intended for system-wide use are installed. Programs compiled from source code are normally installed in /usr/local/bin. On a newly installed Linux system, this tree exists, but it will be empty until the system administrator puts something in it.|
|/usr/sbin|Contains more system administration programs.|
|/usr/share|/usr/share contains all the shared data used by programs in /usr/bin. This includes things such as default configuration files, icons, screen backgrounds, sound files, etc.|
|/usr/share/doc|Most packages installed on the system will include some kind of documentation. In /usr/share/doc, we will find documentation files organized by package.|
|/var|With the exception of /tmp and /home, the directories we have looked at so far remain relatively static, that is, their contents don't change. The /var directory tree is where data that is likely to change is stored. Various databases, spool files, user mail, etc. are located here.|
|/var/log|/var/log contains log files, records of various system activity. These are important and should be monitored from time to time. The most useful ones are /var/log/messages and/or /var/log/syslog though these are not available on all systems. Note that for security reasons, some systems only allow the superuser to view log files.|
|~/.config and ~/.local|These two directories are located in the home directory of each desktop user. They are used to store user-specific configuration data for desktop applications.|
