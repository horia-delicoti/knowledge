# Linux Command Cheat Sheet

## User management commands

```sh
/etc/default/useradd - collection of default values
/etc/login.defs      - configuration control definitions for the login package
```

| Command | Description |
| - | - |
| `sudo adduser username`      | To add a new user                |
| `sudo passwd -l 'username'`  | To change the password of a user |
| `sudo userdel -r 'username'` | To remote a newly create user    |
| `sudo usermod` | Modify a user account |
| `sudo deluser USER GROUPNAME` | To remote a user from a group |
| `finger` | Show information of all the users logged in |
| `who` | Show users logged in the system |
| `whoami` | Current user ID |
| `id` | Get numeric version of the user |
| `passwd` | Change passwords |
| `chage` | Change user password expiry |

### Links

- [Packages Search for Linux and Unix](https://pkgs.org/)
- [YUM command cheat sheet](https://access.redhat.com/sites/default/files/attachments/rh_yum_cheatsheet_1214_jcs_print-1.pdf)
- [Ubuntu packages](https://packages.ubuntu.com/bionic/)
- [How To Delete A Repository And GPG Key In Ubuntu](https://www.ostechnix.com/how-to-delete-a-repository-and-gpg-key-in-ubuntu/)