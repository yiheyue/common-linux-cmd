# Basic commands

## date

> date (1) - print or set the system date and time

print the date of today

```
user@pc ~ $ date
Mon Jan  7 07:23:09 EST 2019
```

## cal

> cal (1) - displays a calendar and the date of Easter

display the calendar of this month

```
user@pc ~ $ cal
    January 2019
Su Mo Tu We Th Fr Sa
       1  2  3  4  5
 6  7  8  9 10 11 12
13 14 15 16 17 18 19
20 21 22 23 24 25 26
27 28 29 30 31
```

## df

> df (1) - report file system disk space usage

display the disk space usage in human readable format

```
user@pc ~ $ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            2.0G     0  2.0G   0% /dev
tmpfs           405M  6.2M  398M   2% /run
/dev/sda1        49G  4.5G   42G  10% /
tmpfs           2.0G  276K  2.0G   1% /dev/shm
tmpfs           5.0M  4.0K  5.0M   1% /run/lock
tmpfs           2.0G     0  2.0G   0% /sys/fs/cgroup
tmpfs           405M   52K  404M   1% /run/user/1000
```

## free

> free (1) - Display amount of free and used memory in the system

display the memory usage in human readable format

```
user@pc ~ $ free -h
              total        used        free      shared  buff/cache   available
Mem:           3.9G        360M        2.8G        7.1M        848M        3.2G
Swap:          974M          0B        974M
```

## exit

exit the terminal

```
user@pc ~ $ exit
```

## Switch to virtual terminals

- First, press `[Ctrl] + [Alt] + [F1 ~ F6]` to switch terminals `tty1` \~ `tty6`.

- Then, press `[Alt] + [F1 ~ F7]` to switch terminals `tty1` to `tty7` (`tty7` is graphical desktop).
