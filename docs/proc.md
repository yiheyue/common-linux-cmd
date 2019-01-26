# Process

## ps

> ps (1) - report a snapshot of the current processes

e.g. show the processes

```
user@pc ~ $ ps
  PID TTY            TIME CMD
 2999 pts/4      00:00:00 bash
 3034 pts/4      00:00:00 ps
```

- PID is short for "Process ID".

- TTY is short for "Teletype".

- TIME is the amount of CPU time consumed by the process.

e.g. show processes regardless of what terminal they are controlled by

```
user@pc ~ $ ps x
  PID TTY      STAT   TIME COMMAND
 1185 ?        Ss     0:00 /lib/systemd/systemd --user
 1186 ?        S      0:00 (sd-pam)
...
...
```

- STAT is short for "State".

Process states

| State | Meaning                                                                                                               |
| ----- | --------------------------------------------------------------------------------------------------------------------- |
| R     | Running. This means that the process is running or ready to run                                                       |
| S     | Sleeping. A process is not running; rather, it is waiting for an event, such as keystroke or network packet           |
| D     | Uninterruptible sleep. Process is waiting for I/O such as a disk drive                                                |
| T     | Stopped. Process has been instructed to stop                                                                          |
| Z     | A defunct or "zombie" process. This is a child process that has terminated, but has not been cleaned up by its parent |
| <     | A high priority process                                                                                               |
| N     | A low priority process                                                                                                |

e.g. `aux` options

```
user@pc ~ $ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.3  0.1  24060  5084 ?        Ss   21:57   0:04 /sbin/init splash
root         2  0.0  0.0      0     0 ?        S    21:57   0:00 [kthreadd]
...
...
```

- USER - User ID. This is the owner of the process.

- %CPU - CPU usage in percent.

- %MEM - Memory usage in percent.

- VSZ - Virtual memory size.

- RSS - Resident set size. The amount of physical memory (RAM) the process is using in kilobytes.

- START - Time when the process started.

## top

> top (1) - display Linux processes

e.g. show the dynamic view of the machine's activity

```
user@pc ~ $ top
...
...
```

- type `h` to display the program's help screen

- type `q` to quit top

## Control a process

- Start it - `$ xlogo`

- Interrupt it - press [Ctrl + c]

- Run a process in the background - `$ xlogo &`

- Move a process to the foreground - `$ fg %1`

- Stop a process - press [Ctrl + z], usually stop a process, then move it to the background

- Terminate a process - `$ kill 1931`

## jobs

> jobs (built-in) - Display status of jobs

e.g. display current jobs

```
user@pc ~ $ jobs
[1]+ Running      xlogo &
```

## fg

> fg (built-in) - Move job to the foreground

e.g. move xlogo to the foreground

```
user@pc ~ $ fg %1
```

## bg

> bg (built-in) - Move job to the background

e.g. move xlogo to the background

```
user@pc ~ $ bg %1
```

## kill

> kill (1) - send a signal to a process

e.g. terminate a process (PID = 1931)

```
user@pc ~ $ kill 1931
```

## Signal

- [Ctrl + c] - INT (Interrupt)

- [Ctrl + z] - TSTP (Terminal Stop)

## killall

> killall (1) - kill processes by name

## pstree

> pstree (1) - display a tree of processes

## vmstat

> vmstat (1) - Report virtual memory statistics

## xload

## tload

> tload (1) - graphic representation of system load average
