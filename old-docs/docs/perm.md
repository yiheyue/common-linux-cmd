# Permission

## id

> id (1) - print real and effective user and group IDs

e.g. print current user and group ID

```
user@pc ~ $ id
uid=1000(user) gid=1000(user) groups=1000(user),4(adm)...
```

- /etc/passwd - users information file

- /etc/group - groups information file

- /etc/shadow - users password file

## File mode

```
Owner   Group   World
rwx     rwx     rwx
```

The nine characters (rwxrwxrwx) are called the file mode.

- r for read

- w for write

- x for execute

Permission attributes

| Attributes | Files | Directories |
| ---------- | ----- | ----------- |
| r          | Allows a file to be opened and read | Allows a directory's contents to be listed if the execute attribute is also set |
| w          | Allows a file to be written to or truncated, however this attribute does not allow files to be renamed or deleted. The ability to delete or rename files is determined by directory attributes | Allows files within a directory to be created, deleted, and renamed if the execute attribute is also set |
| x          | Allows a file to be treated as a program and executed. Program files written in scripting languages must also be set as readable to be executed | Allows a directory to be entered |

## chmod

> chmod (1) - change file mode bits

The `chmod` command supports two distinct ways of specifying mode changes: **octal number representation**, or **symbolic representation**.

### Octal number representation

Mapping table

| Octal | Binary | File mode |
| ----- | ------ | --------- |
| 0     | 000    | ---       |
| 1     | 001    | --x       |
| 2     | 010    | -w-       |
| 3     | 011    | -wx       |
| 4     | 100    | r--       |
| 5     | 101    | r-x       |
| 6     | 110    | rw-       |
| 7     | 111    | rwx       |

e.g. change the file mode of foo file

```
user@pc ~ $ ls -l foo
-rw-rw-r-- 1 user user 0 Jan 23 02:21 foo
user@pc ~ $ chmod 770 foo
user@pc ~ $ ls -l foo
-rwxrwx--- 1 user user 0 Jan 23 02:21 foo
```

### Symbolic representation

Object mapping table

| Notaion | Meaning                                                 |
| ------- | ------------------------------------------------------- |
| u       | Short for "user", but means the file or directory owner |
| g       | Short for "group", means group                          |
| o       | Short for "others", means world                         |
| a       | Short for "all", the combination of "u", "g" and "o"    |

Operation mapping table

| Notaion | Meaning |
| ------- | ------- |
| +       | add     |
| -       | remove  |
| =       | assign  |

e.g. change the file mode of foo file

```
user@pc ~ $ ls -l foo
-rwxrwxrwx 1 user user 0 Jan 23 02:21 foo
user@pc ~ $ chmod o-rwx foo
user@pc ~ $ ls -l foo
-rwxrwx--- 1 user user 0 Jan 23 02:21 foo
```

There are three special permissions:

1. `setuid` bit (Octal 4000)

2. `setgid` bit (Octal 2000)

3. `sticky` bit (Octal 1000)

## umask

> umask (built-in) - Display or set file mode mask

e.g. display file mode mask

```
user@pc ~ $ umask
0002
```

e.g. set file mode mask

```
user@pc ~ $ umask 0000
```

## Change identity

There are three ways to take on an alternate identity:

1. Log out and log back in as the alternate user

2. Use the `su` command

3. Use the `sudo` command

## su

> su (1) - change user ID or become superuser

e.g. become superuser

```
user@pc ~ $ su -
Password:
root@pc ~ #
```

e.g. execute a single command

```
user@pc ~ $ su -c 'ls -l /root/*'
Password:
...
...
```

## sudo

> sudo (8) - execute a command as another user

## chown

> chown (1) - change file owner and group

e.g. change the ownership of the file from its current owner to user bob

```
user@pc ~ $ chown bob foo
```

## chgrp

> chgrp (1) - change group ownership

## passwd

> passwd (1) - change user password

## adduser

> adduser (8) - add a user or group to the system

## useradd

> useradd (8) - create a new user or update default new user information

## groupadd

> groupadd (8) - create a new group