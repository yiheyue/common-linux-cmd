# 基础命令

## 显示日期

- date

    date 命令用于显示当天的日期

    ```bash
    tony@pc:~$ date
    Fri Mar 15 20:32:43 CST 2019
    ```

- cal

    cal 命令用于显示当月的日历

    ```bash
    tony@pc:~$ cal
        March 2019       
    Su Mo Tu We Th Fr Sa  
                    1  2  
    3  4  5  6  7  8  9  
    10 11 12 13 14 15 16  
    17 18 19 20 21 22 23  
    24 25 26 27 28 29 30  
    31                    
    ```

    显示当年具体月份的日历（例如：显示当年 12 月的日历）

    ```bash
    tony@pc:~$ cal -m 12
      December 2019      
    Su Mo Tu We Th Fr Sa  
    1  2  3  4  5  6  7  
    8  9 10 11 12 13 14  
    15 16 17 18 19 20 21  
    22 23 24 25 26 27 28  
    29 30 31              
    ```

    显示指定年份的整年日历（例如：显示 2020 年的日历）

    ```bash
    tony@pc:~$ cal -y 2020
                                2020
          January               February               March          
    Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  Su Mo Tu We Th Fr Sa  
              1  2  3  4                     1   1  2  3  4  5  6  7  
    5  6  7  8  9 10 11   2  3  4  5  6  7  8   8  9 10 11 12 13 14  
    12 13 14 15 16 17 18   9 10 11 12 13 14 15  15 16 17 18 19 20 21  
    19 20 21 22 23 24 25  16 17 18 19 20 21 22  22 23 24 25 26 27 28  
    26 27 28 29 30 31     23 24 25 26 27 28 29  29 30 31              
    ...
    ```

## 查看硬件信息

- df

    df 命令用于汇报系统磁盘空间的使用情况（默认单位是 1KB）

    ```bash
    tony@pc:~$ df
    Filesystem     1K-blocks     Used Available Use% Mounted on
    udev             6069336        0   6069336   0% /dev
    tmpfs            1218296     2044   1216252   1% /run
    /dev/sdb1      960348184 20970372 890525076   3% /
    tmpfs            6091476    10932   6080544   1% /dev/shm
    ...
    ```

    以 1024 作为进制单位显示磁盘空间的使用情况

    ```bash
    tony@pc:~$ df -h
    Filesystem      Size  Used Avail Use% Mounted on
    udev            5.8G     0  5.8G   0% /dev
    tmpfs           1.2G  2.0M  1.2G   1% /run
    /dev/sdb1       916G   20G  850G   3% /
    tmpfs           5.9G   11M  5.8G   1% /dev/shm
    tmpfs           5.0M  4.0K  5.0M   1% /run/lock
    ...
    ```

    以 1000 作为进制单位显示磁盘空间的使用情况

    ```bash
    tony@pc:~$ df -H
    Filesystem      Size  Used Avail Use% Mounted on
    udev            6.3G     0  6.3G   0% /dev
    tmpfs           1.3G  2.1M  1.3G   1% /run
    /dev/sdb1       984G   22G  912G   3% /
    tmpfs           6.3G   11M  6.3G   1% /dev/shm
    tmpfs           5.3M  4.1k  5.3M   1% /run/lock
    ...
    ```

- free

    free 命令用于显示系统内存的使用情况

    ```bash
    tony@pc:~$ free -h
                  total        used        free      shared  buff/cache   available
    Mem:            11G        1.9G        4.6G        600M        5.1G        8.9G
    Swap:          2.0G          0B        2.0G
    ```

## 目录切换

- pwd

    pwd 命令用于打印出当前工作目录

    ```bash
    tony@pc:~$ pwd
    /home/tony
    ```

- cd

    cd 命令用于切换目录

    ```bash
    tony@pc:~$ cd /usr/local/bin/
    ```

    | 常用命令 | 作用                  |
    | ------- | -------------------- |
    | cd      | 切换到当前用户的家目录   |
    | cd -    | 切换到上一个目录        |
    | cd ~bob | 切换到 bob 用户的家目录 |

- ls

    ls 命令用于列出当前目录中的内容

    ```bash
    tony@pc:~$ ls
    ...
    ```

    | 常用命令 | 作用                  |
    | ------- | -------------------- |
    | ls -a   | 列出所有的文件          |
    | ls -F   | 在目录后面加一个斜杠 `/` |
    | ls -h   | 以人类可读的方式显示     |
    | ls -l   | 以长格式显示结果        |
    | ls -r   | 以相反的顺序显示结果     |
    | ls -S   | 按文件大小来排序         |
    | ls -t   | 按照修改时间来排序       |

## 查看文件

- file

    file 命令用于显示文件的类型

    ```bash
    tony@pc:~$ file cmd-list.md
    cmd-list.md: ASCII text
    ```

- less

    less 命令用于显示文件的内容（more 命令的升级版）

    ```bash
    tony@pc:~$ less cmd-list.md
    ...
    ```

    | less 中的常用命令 | 作用                        |
    | --------------- | --------------------------- |
    | [space]         | 向下翻页                     |
    | b               | 向上翻页                     |
    | j               | 向下滚动一行                 |
    | k               | 向上滚动一行                 |
    | g               | 移动到文件的开头一行           |
    | G               | 移动到文件的末尾一行           |
    | h               | 显示帮助                     |
    | q               | 退出 less 程序               |
    | /user           | 向前查找 user 字符串          |
    | n               | 向前查找下一个被指定查找的字符串 |