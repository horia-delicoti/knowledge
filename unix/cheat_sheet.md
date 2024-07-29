# Linux Command Cheat Sheet

- [cheat.sh](http://cheat.sh/)
- [tldr pages](https://tldr.sh/)
- [dev toolbox](https://www.devtoolbox.co/tools/diff-viewer)
- [crontab guru](https://crontab.guru/)

## User management and logging in

```sh
/etc/default/useradd # collection of default values
/etc/login.defs      # configuration control definitions for the login package
/etc/passwd          # detailed list of users accounts on the system
/etc/group           # list of groups
/etc/shadow          # store encrypted user passwords
/etc/sudoers         # file used to allocate system rights to system users
/etc/skel            # files and dir to ensure that all users gets same initial settings
```

| Command | Description |
| - | - |
| `sudo adduser username`      | to add a new user                |
| `sudo passwd -l 'username'`  | to change the password of a user |
| `sudo userdel -r 'username'` | to remote a newly create user    |
| `sudo usermod` | modify a user account |
| `sudo deluser USER GROUPNAME` | to remote a user from a group |
| `sudo groupadd GROUPNAME` | to add a new group |
| `sudo groupmod` | change group |
| `sudo groupdel` | delete group |
| `finger` | show information of all the users logged in |
| `who` | show users logged in the system |
| `whoami` | current user ID |
| `id` | get numeric version of the user |
| `passwd` | change passwords |
| `chage` | change user password expiry |
| `gpasswd` | administer /etc/group and /etc/gshadow |

## Files, directories, hard and soft links

| Command | Description |
| - | - |
| `ls -l` | show file type and access permission |
| `chown 'user'` | change ownership of file/directory |
| `chgrp group 'file'` | change the group for a file |
| `umask` | set file mode creation mask |
| `ln '<full_path>/file' '<full_path>/new file'` | create hard link |
| `ln -sf '<full_path>/file' '<full_path>/new file path'` | create soft link |
| `pwd` | print name of current/working directory |
| `mkdir` | create new directory |

## File permission, search for files

| Command | Description |
| - | - |
| `getfacl` | get file access control lists |
| `setfacl` | set file access control lists |
| `chmod <g or u>+s 'file'` | setuid: a bit that makes an executable run with the privileges of the owner/group of the file |
| `chmod +t 'file'` | sticky bit: a bit set on directories that allows only the owner or root can delete files and subdirectories |
| `lsattr` | lists file attributes (read (r), write (w), execute (x)) |
| `chattr` | modifies the attributes of files |
| `find` | search for files in a directory hierarchy |

## File content

| Command | Description |
| - | - |
| `cat` | concatenate files and print on the standard output |
| `head` | output the first part of files |
| `tail` | output the last part of files |
| `sed` | stream editor for filtering and transforming text |
| `awk` | pattern scanning and text processing language |
| `grep` | print lines that match patterns |
| `diff` | compare files |
| `cut` | remove sections from each line of files |
| `wc` | counts characters, lines, and words |
| `sort` | sort lines of text files |

## Archive, back up, compress, IO redirection

| Command | Description |
| - | - |
| `tar` | archiving utility |
| `gzip` | compress or expand files |
| `tee` | redirects standard input to both standard output and one or more files |
| `tr` | finds-and-replaces one string with another |
| `<` | standard input |
| `>` or `1>` | redirect standard output |
| `2>` | redirect standard error |
| `2>&1` | redirect standard error to standard output |
| `\|` | pipes are used to redirect a stream from one program to another |

## Git, SSL certificates

| Command | Description |
| - | - |
| `git` | version control |
| `openssl` | used for cryptography functions of OpenSSL's crypto library from the shell |

## Boot and Change Operating Modes, Troubleshoot Botloaders

```sh
/etc/default/grub # file to edit on a system booting through legacy BIOS
/boot/grub/grub.cfg
/etc/fstab #  configuration table designed for mounting and unmounting file systems to a machine at boot
```

| Command | Description |
| - | - |
| `shutdown` | Halt, power-off or reboot the machine |
| `grub2-install` | Install GRUB on a device |
| `grub-mkconfig -o /boot/grub/grub.cfg`| to update grub |
| `systemctl get-default` | get default boot target value |
| `systemctl set-default <graphical.target>` | change boot in graphical |

## Scripting, Services and Analyze Log Files

```sh
/var/log/ # directory contains the logs of most of the services running on a Linux system
/var/log/syslog # stores global system activity data, startup messages (Debian/Ubuntu)
/var/log/messages # stores global system activity data, startup messages (CentOS)
/var/log/auth.log # store all security-related events such as logins, root users actions (Debian/Ubuntu)
/var/log/secure # store all security-related events such as logins, root users actions (CentOS)
/var/log/kern.log # stores kernel events, errors and warning logs
/var/log/cron # stores info about scheduled tasks (cron jobs)
```

| Command | Description |
| - | - |
| `./script.sh` | run script |
| `systemctl` | control the systemd system and service manager |
| `journalctl` | [systemd's logging service](https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs) |
| `dmesg`| print or control the kernel ring buffer |

## Manage Processes and Monitoring

```sh
/proc/<pid>/task # filesystem can be helpful in monitoring process
```

| Command | Description |
| - | - |
| `top` | process activity, dynamically updated |
| `uptime` | how long the system is running and the average load |
| `ps -aux` | details about the current processes |
| `pstree -aAp <pid>` | a tree of process and their connections |
| `pgrep` | look up, signal, or wait for processes based on name and other attributes |
| `mpstat` | multiple process usage |
| `iostat` | CPU utilization and I/O statistics |
| `kill` | send a signal to a process |
| `nice` | run a program with modified scheduling priority |
| `renice` | alter priority of running processes |
| `lsof` | list open files |
| `sleep` | delay for a specified amount of time |
| `sar` | display and collect information about system activity |
| `numastat` | display and collect information about system activity |
| `strace` | information about all system calls a process makes |

## Schedule tasks

```sh
/etc/crontab # system wide crontab
/var/log/cron # contains the information about anacron jobs run
```

| Command | Description |
| - | - |
| `crontab -e` | maintain crontab files for individual users |
| `anacron -n -f` | anacron runs commands periodically; rerun all jobs, regardless of when they were last executed |
| `at, batch, atq, atrm` | queue, examine, or delete jobs for later execution |

## Manage Software, Repositories & Install Software from Source

```sh
/etc/apt/source.list #  list of configured APT (Advanced Package Tool) data sources to fetch packages
/etc/yum.repos.d/ # directory to add repositories
/etc/yum.conf # configuration file for yum
```

| Command | Description |
| - | - |
| `dnf, yum` | install, update, remove and manage packages on the RPM-based operating system (CentOS, Fedora) |
| `apt` | install, upgrade, remove and manage packages on the Ubuntu system |
| `dpkg --search /bin/ls` | finding the name of the package that "/bin/ls" belongs to (Ubuntu) |
| `rpm -qf` | finding the name of the package that "/bin/ls" belongs (CentOS) |

## Kernel Runtime Parameters, SELinux/AppArmor, Security and User Resource Limits

```sh
/etc/sysctl.conf # used to override default kernel parameter values and make changes persistent
/etc/security/limits.conf # file sets the resource limits for the users.
/etc/sudoers         # control who can run what commands as what users on what machines
```

| Command | Description |
| - | - |
| `ps auxZ` | get SELinux label of a process |
| `ls -Z` | get SELinux label for a file |
| `chcon -t` | change file security context |
| `restorecon` | restore the correct (default) labels for every file |
| `setenforce 0` | temporarily change the SELinux status to Permissive on this system |
| `semanage user -l` | identify the SELinux Roles for user |
| `sysctl -a` | configure kernel parameters at runtime |
| `ulimit` | get and set user limits |
| `visudo` | checks the file syntax before overwritting sudoers file  |

## Manage Containers and VMs

| Command | Description |
| - | - |
| `docker` | docker image and container command line interface |
| `qemu` | full-system emulation |
| `virsh` | the main interface for managing virsh guest domains |

## System-Wide Environment Profiles and Template User Environments

```sh
/etc/environment # is used to set the globally available environment variables in a Linux-based system
/etc/profile.d/welcome.sh # command gets executed for any user that logs in to the system
/etc/skel # a new user account is added to the system, a file called README is copied to the new 
~/.bashrc # script file that’s executed when a user logs in
```

| Command | Description |
| - | - |
| `env` | prin environment variables |
| `echo $VAR` | print environment variable |
| `set <varname>=<value>` | set a local variable |
| `export <varname>=<value>`| sets the variable and exports it to the global environment (available to other processes) |
| `source /etc/environment` | execute the command on the terminal for the changes to take effect |

## Manage Partitions and Swap Space

```sh
/dev/ # dev files are abstractions of standard devices that applications interact with via I/O system calls
/proc/partitions
```

| Command | Description |
| - | - |
| `fdisk -l` | list all disks with all partitions and size of each |
| `cfdisk` | display or manipulate a disk partition table|
| `lsblk -f` | list block devices |
| `mkswap` | set up a Linux swap area |
| `swapon, swapoff` | enable/disable devices and files for paging and swapping |

## Filesystems, Mount at Boot, Mount options

```sh
/etc/fstab # filesystems it automatically mounts when it boots up
```

| Command | Description |
| - | - |
| `lshw -short -C disk` | display each disk device |
| `hdparm -i /dev/sda` |  get details of specific SATA disk |
| `blkid` | # lists each partition's unique identifier (UUID) and its filesystem type |
| `df -h` | # list of mounted filesystems, their mount points, and space used |
| `du -sh` | # estimate file space usage |
| `lsusb` | # list of all USB and PCI buses and devices |
| `hdparm` | # list info about sata devices like hdd |
| `mount` | column -t # mount a filesystem |
| `lscpi` | |
| `cryptsetup` | manage plain dm-crypt and LUKS encrypted volumes |
| `mkfs.ext4` | create an ext4 file system |

## Manage LVM

| Command | Description |
| - | - |
| `pvs` | display information about physical volumes |
| `vgs` | Display information about volume groups |
| `pvcreate` | initialize physical volume(s) for use |
| `pvremove` | remove  LVM  label(s) from physical volume(s) |
| `vgcreate` | create a volume group |
| `vgextend` | add physical volumes to a volume group |
| `vgreduce`| remove  physical volume(s) from a volume group |
| `lvcreate` | create a logical volume |
| `lvresize` | resize a logical volume |

## Configure Networking, Status of Network Services

```sh
/etc/hosts # mapping hostnames to IP address; local DNS entries
/etc/resolve.conf # holds configuration info for DNS resolution
/etc/hostname # contains the hostname
```

| Command | Description |
| - | - |
| `ip route` or `route -n` | display the routing table, default gateway |
| `hostnamectl` | query and modify system's hostname |
| `firewall-cmd` | managing firewall configuration |
| `timedatectl` | query and modify system's time and date settings |
| `ss -tunlp` | investigate sockets and check processes on system's incoming network connections |
| `ip` | show routing, network devices, interfaces and tunnels |
| `ip route show` | identify the default gateway |

## Packet Filtering

| Command | Description |
| - | - |
| `ufw` | program for managing a netfilter firewall |
| `iptables` | administration tool for IPv4/IPv6 packet filtering and NAT |
| `wireshark` | analyzes network traffic in real-time  |

## SSH

```sh
/etc/ssh/ssh_config # ssh client system-wide configuration file
/etc/ssh/sshd_config #  sshd server system-wide configuration file
```

| Command | Description |
| - | - |
| `ssh` | openssh remote login client |

## DNS

```sh
/etc/named.conf # config file used by BIND
/var/named # store all zone files and related data by BIND DNS server
```

| Command | Description |
| - | - |
| `dig` | allows users to run DNS queries and view server output |
| `host` | converts hostnames to IP addresses |
| `nslookup` | queries DNS servers for information about hosts and domains |

## Hardware

| Command | Description |
| - | - |
| `hwinfo --short` | probe for hardware |
| `lshw --short` | list hardware |
| `lspci` | list all PCI devices |

CPU

```sh
cat /proc/cpuinfo
cat /proc/version
```

| Command | Description |
| - | - |
| `lscpu` | display information about CPU architecture |
| `lshw -C cpu` | list hardware |

Memory

```sh
cat /proc/meminfo
```

| Command | Description |
| - | - |
| `htop` | more details about memory, CPU, process ID, user ID and command running |
| `lshw -short -C memory` | system memory, including type, size, speed |
| `dmidecode -t memory \| grep -i size` | list each memory stick and its capacity |
| `free -m` | show current memory use |

## Links

- [Packages Search for Linux and Unix](https://pkgs.org/)
- [YUM command cheat sheet](https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf)
- [Ubuntu packages](https://packages.ubuntu.com/bionic/)
- [How To Delete A Repository And GPG Key In Ubuntu](https://www.ostechnix.com/how-to-delete-a-repository-and-gpg-key-in-ubuntu/)
