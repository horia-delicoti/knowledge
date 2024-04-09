# Linux

- [Linux](https://github.com/torvalds/linux)

- [The Linux Programming Interface](https://man7.org/tlpi/)
- [Linux system administration essentials LFS207](https://training.linuxfoundation.org/training/linux-system-administration-essentials-lfs207/) - [E-Learning Classes](https://trainingportal.linuxfoundation.org/learn/course/linux-system-administration-essentials-lfs207/course-introduction/course-information) - [LFS207 Class Forum](https://forum.linuxfoundation.org/categories/lfs207-class-forum)

## Kernel

- [Kernel newbies](https://kernelnewbies.org/)
- [The Linux Kernel documentation](https://www.kernel.org/doc/html/latest/)

## Notes

## Links

- [Filesystem Hierarchy Standard document](https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.pdf)
- [Test your sysadmin skills](https://github.com/trimstray/test-your-sysadmin-skills)
- [Linux inside](https://0xax.gitbooks.io/linux-insides/content/index.html)
- [apt](https://yoshuawuyts.gitbooks.io/knowledge/content/bin/apt.html)

## Commands

### Hardware

```sh
hwinfo --short # probe for hardware
lshw -short # list hardware
lspci # list all PCI devices
```

CPU

```sh
lscpu # display information about CPU architecture
lshw -C cpu
cat /proc/cpuinfo
cat /proc/version
```

Memory

```sh
htop # more detail about memory, CPU, process ID, user ID and commands being run. 
lshw -short -C memory # system memory, including type, size, speed
dmidecode -t memory | grep -i size # To list each memory stick and its capacity
free -m # show current memory use 
cat /proc/meminfo
```

### Disks, filesystems, and devices

```sh
lshw -short -C disk # display each disk device
hdparm -i /dev/sda # get details of specific SATA disk
lsblk # list all disks with all partitions and size of each
blkid # lists each partition's unique identifier (UUID) and its filesystem type
df -h # list of mounted filesystems, their mount points, and space used
lsusb # list of all USB and PCI buses and devices
hdparm # list info about sata devices like hdd
mount | column -t # mount a filesystem
lscpi 
cat /proc/partitions
```

### Network

```sh
sudo lshw -C network # hardware details about network card
netstat -r # show default gateway and routing iptables
ip route | column -t

# show network interfaces
ifconfig -a
ip link show
netstat -i
```

### Software

```sh
uname -a # Show kernel version, network hostname, more
cat /etc/os-release # Get OS release version
dmidecode -t bios # Display UEFI/BIOS info
```

### User Management

```sh
sudo useradd <user> # Create user account
sudo userdel <user> # Delete user account
sudo usermod -L <user> # Change characteristics of a user account
sudo chage # Change user password expiry information
passwd <user> # Change password
who # Users currently looged in the system
whoami # Current user id
id # Current user ID, group ID, ...
groups # Show groups membership
groupadd # Add a new group
groupmod # Modify a group's attributes
groupdel # Remove a group
usermod # Manage a user's group memberships
```
