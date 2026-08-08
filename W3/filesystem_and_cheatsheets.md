
### Linux File Structure

Linux is CaSe-SenSiTive.

###   The Filesystem Hierarchy 
Linux have no drive letters.
It sart from root directory **/**.
Removable Drives are mounted under /media, e.g. cdrom

**/home** – contains all user home directories
e.g. /home/<USERNAME> contains files of a specific user

### Important directories
*(Do not mess with these directories!)
**/bin** : Command binaries files (OS)
**/usr/bin**: Command binaries that are not essential enough to place into /bin 
**/boot**: Static files of the boot loader. Stores data that is used before the kernel begins executing user-mode programs. 
**/sbin**: System binaries. Programs necessary for the boot loader 
**/lib**: kernel modules and those shared library images
**/opt, /var/opt**: reserved for all the software and add-on packages that are not part of the default installation. Stuff you install yourself.

**/proc**: Not really a directory. Very special virtual filesystem. 
Sometimes referred to as a process information pseudo-file system.
(READ ONLY. Do not mess with this directory!)
Every number is actually a process id. (see ps)

**/dev** : directory is the location of special or device files.
Tip: Everything in Linux is a file or a directory!
/dev/hd_ - hard disk
/dev/hda – Primary hard disk
/dev/hda1 – Primary hard disk, Partition 1
/dev/cdrom – CD/DVD drive
/dev/fd - floppy drive
/dev/dsp – audio device (speaker)
/dev/lp – printer, parallel port
/dev/tty – terminals or console

**/etc** - contains all system related configuration files
/etc/fstab – [FileSystem TABle] filesystems mounted automatically at startup
/etc/group - lists user groups and who belongs to them.
/etc/hostname – machine hostname
/etc/passwd - contains the user database, with fields giving the username, real name, home directory, and other information about each user. Does not actually contain password.
/etc/sudoers - Sudoers file. This file must be edited with the 'visudo' command as root. The sudo command allows an authenticated user to execute an authorized command as root.
/etc/syslog.conf - Lists where log files should go, what messages are written to them and the level of verbosity.
/etc/timezone - local timezone.
/etc/rc - directories contain all the files necessary to control system services and configure runlevels.

### Bash shell script cheat sheet
https://linuxize.com/cheatsheet/bash/
https://github.com/RehanSaeed/Bash-Cheat-Sheet

