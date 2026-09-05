

## FS (A tour on where everything lives in Linux)

### Linux File Structure

Linux is CaSe-SenSiTive.

###   The Filesystem Hierarchy 

- Linux have no drive letters.
<br/>
- It starts from root directory **/**.
<br/>
- Removable Drives are mounted under /media, e.g. cdrom
<br/>
- **/home** – contains all user home directories
<br/>e.g. /home/<USERNAME> contains files of a specific user

---
### Important directories
*(Do not mess with these directories!)

- **/bin** : Command binaries files (OS)
<br/>
- **/usr/bin**: Command binaries that are not essential enough to place into /bin 
<br/>
- **/boot**: Static files of the boot loader. Stores data that is used before the kernel begins executing user-mode programs. 
<br/>
- **/sbin**: System binaries. Programs necessary for the boot loader 
<br/>
- **/lib**: kernel modules and those shared library images
<br/>
- **/opt, /var/opt**: reserved for all the software and add-on packages that are not part of the default installation. Stuff you install yourself.
<br/>
- **/proc**: Not really a directory. Very special virtual filesystem. 
<br/>Sometimes referred to as a process information pseudo-file system.
<br/>(READ ONLY. Do not mess with this directory!)
<br/>Every number is actually a process id. (see ps)

---
### Devices aka peripherals
- **/dev** : directory is the location of special or device files.
<br/>Tip: Everything in Linux is a file or a directory!
<br/>
- /dev/hd_ - hard disk
<br/>
- /dev/hd*a* – Primary hard disk
<br/>
- /dev/hd*a1* – Primary hard disk, Partition 1
<br/>
- /dev/cdrom – CD/DVD drive
<br/>
- ~~/dev/fd - floppy drive~~
<br/>
- /dev/dsp – audio device (speaker)
<br/>
- /dev/lp – printer, parallel port
<br/>
- /dev/tty – terminals or console

---
### System Configuration files
- **/etc** - contains all system related configuration files
<br/>
- /etc/fstab – [FileSystem TABle] filesystems mounted automatically at startup
<br/>
- /etc/group - lists user groups and who belongs to them.
<br/>
- /etc/hostname – machine hostname
<br/>
- /etc/passwd - contains the user database, with fields giving the username, real name, home directory, and other information about each user. Does not  actually contain password.
<br/>
- /etc/syslog.conf - Lists where log files should go, what messages are written to them and the level of verbosity.
<br/>
- /etc/timezone - local timezone.
<br/>
- /etc/rc - directories contain all the files necessary to control system services and configure runlevels.

---
### Ref: Bash shell script cheat sheet
* https://linuxize.com/cheatsheet/bash/
* https://github.com/RehanSaeed/Bash-Cheat-Sheet


---
