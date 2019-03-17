# 进程

- ps

    ps （process status）命令常用于查看进程

    ```bash
    tony@pc:~$ ps
     PID TTY          TIME CMD
    3604 pts/1    00:00:00 bash
    4814 pts/1    00:00:00 ps
    ```

    使用 `x` 选项展示所有的进程

    ```bash
    tony@pc:~$ ps x
     PID TTY      STAT   TIME COMMAND
    1665 ?        Ss     0:00 /lib/systemd/systemd --user
    1666 ?        S      0:00 (sd-pam)
    ...
    ```

    常用选项 `aux`

    ```bash
    tony@pc:~$ ps aux
    USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    root         1  0.0  0.0 225556  9268 ?        Ss   10:45   0:02 /sbin/init spla
    root         2  0.0  0.0      0     0 ?        S    10:45   0:00 [kthreadd]
    root         3  0.0  0.0      0     0 ?        I<   10:45   0:00 [rcu_gp]
    ```

- top

    top 命令用于动态地查看进程

    ```bash
    tony@pc:~$ top
    ```

    查看帮助按 `h`，退出 top 按 `q`

- jobs

    jobs 命令用于查看任务状态

    ```bash
    tony@pc:~$ jobs
    ```

- fg

    fg 命令用于将任务移动至前台（例如，将任务号为 1 的任务移动至前台）

    ```bash
    tony@pc:~$ fg %1
    ```

- bg

    bg 命令用于将任务移动至后台（例如，将任务号为 1 的任务移动至后台）

    ```bash
    tony@pc:~$ bg %1
    ```

- kill

    kill 命令用于向进程发送 signal（信号）

    - Ctrl-c 对应 INT（Interrupt）信号

    - Ctrl-z 对应 TSTP（Terminal Stop）信号

    常用信号

    | 编号 | 名字  | 含义                              |
    | --- | ----- | -------------------------------- |
    | 1   | HUP   | 即 Hangup，挂起                   |
    | 2   | INT   | 即 Interrupt，中断                |
    | 3   | QUIT  | 即 Quit，退出                     |
    | 9   | KILL  | 即 Kill，杀死                     |
    | 11  | SEGV  | 即 Segmentation Violation，段错误 |
    | 15  | TERM  | 即 Terminate，终止                |
    | 18  | CONT  | 即 Continue，继续                 |
    | 19  | STOP  | 即 Stop，停止                     |
    | 20  | TSTP  | 即 Terminal Stop，终端停止         |
    | 28  | WINCH | 即 Window Change，窗口大小改变      |

    使用 kill 命令将 PID 为 5097 的进程挂起

    ```bash
    tony@pc:~$ kill -1 5097
    ```

关于进程管理的其他命令：

- killall

- pstree

- vmstat

- xload

- tload