# Linux Command Cheat Sheet

## User management commands

```sh
/etc/default/useradd - collection of default values
/etc/login.defs      - configuration control definitions for the login package
/etc/passwd
/etc/group
/etc/shadow
/etc/sudoers         - file used to allocate system rights to system users
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

## Files, directories, permission, hard and soft links

| Command | Description |
| - | - |
| `ls -l` | show file type and access permission |
| `chown 'user'` | change ownership of file/directory |
| `chown user:group 'file'` | change the user as well as group for a file or directory |
| `chgrp group 'file'` | change the group for a file |
| `umask` | set file mode creation mask |
| `getfacl` | get file access control lists |
| `setfacl` | set file access control lists |
| `setuid` | set user identity |
| `setgid` | set group indentity  |

## Process

| Command | Description |
| - | - |
| `ps` | |
| `ps` | |
| `ps` | |
| `ps` | |
| `nproc` | print the number of processing units available |
| `ps` | |
| `ps` | |


## Filesystem

| Command | Description |
| - | - |
| `stat` | |

## Filesystem

| Command | Description |
| - | - |
| `stat` | |

## Security

```sh
/etc/security/limits.conf  - file sets the resource limits for the users.
```

| Command | Description |
| - | - |
| `ulimit` | get and set user limits |

### Links

- [Packages Search for Linux and Unix](https://pkgs.org/)
- [YUM command cheat sheet](https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf)
- [Ubuntu packages](https://packages.ubuntu.com/bionic/)
- [How To Delete A Repository And GPG Key In Ubuntu](https://www.ostechnix.com/how-to-delete-a-repository-and-gpg-key-in-ubuntu/)