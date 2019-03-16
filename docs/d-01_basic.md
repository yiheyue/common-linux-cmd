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

- cat

    cat 命令可以用于查看文件的内容（例如：查看 foo 文件的内容）

    ```bash
    tony@pc:~$ cat foo
    hello world
    ```

- head

    head 命令用于显示文件的头部内容（默认是开头 10 行，如果要自己指定显示行数，需要加 `-n` 选项）

    ```bash
    tony@pc:~$ head -n 20 foo
    hello world
    hello world
    ...
    ```

- tail

    tail 命令用于显示文件的尾部内容（默认是末尾 10 行，如果要自己指定显示行数，需要加 `-n` 选项）

    ```bash
    tony@pc:~$ tail -n 20 foo
    hello world
    hello world
    ...
    ```

- wc

    wc 命令用于统计文本内容的行数、单词数及文本大小

    ```bash
    tony@pc:~$ wc foo
     2  2 12 foo
    ```

## 操作文件

- mkdir

    mkdir 命令用于创建新的目录

    ```bash
    tony@pc:~$ mkdir dirname
    ```

    创建多个目录

    ```bash
    tony@pc:~$ mkdir dirname1 dirname2
    ```

    创建有父子关系的目录

    ```bash
    tony@pc:~$ mkdir dir1/dir2/dir3 dir4
    ```

- cp

    cp 命令用于复制文件或目录（例如：给 README.md 文件备份）

    ```bash
    tony@pc:~$ cp README.md README.md.backup
    ```

    将 README.md 和 source.js 文件复制到 src 目录中

    ```bash
    tony@pc:~$ cp README.md source.js src
    ```

    使用 `-i` 选项提示用户确认是否要重写文件（例如：foo 文件已存在，将 new_foo 复制一个名为 foo 的副本）

    ```bash
    tony@pc:~$ cp -i new_foo foo
    cp: overwrite 'foo'? y
    ```

    使用 `-r` 选项递归地复制目录及目录中的内容（例如：将目录 dir1 以及其内的文件复制到 dir2 中）

    ```bash
    # dir2 存在时，将 dir1 目录挂载在 dir2 下
    tony@pc:~$ cp -r dir1 dir2
    ```

    ```bash
    # dir2 不存在时，将 dir1 中的内容挂载在 dir2 下
    tony@pc:~$ cp -r dir1 dir2
    ```

    使用 `-u` 选项让新的文件覆盖已存在的文件

    ```bash
    tony@pc:~$ cp -u foo1 foo2 dir
    ```

    使用 `-v` 选项显示翔实的命令操作信息

    ```bash
    tony@pc:~$ cp -v foo1 foo2 dir
    'foo1' -> 'dir/foo1'
    'foo2' -> 'dir/foo2'
    ```

- mv

    mv 命令用于移动和重命名文件（例如：将 profile 重命名为 new_profile）

    ```bash
    tony@pc:~$ mv profile new_profile
    ```

    将 config 和 foo_settings 文件移动到 dconf 目录中

    ```bash
    tony@pc:~$ mv config foo_settings dconf
    ```

    将目录 dconf 重命名为 dconfs

    ```bash
    tony@pc:~$ mv dconf dconfs
    ```

    将目录 dconfs 目录及其中的文件移动到 all 目录下

    ```bash
    tony@pc:~$ mv dconfs all
    ```

    mv 命令有着和 cp 命令功能类似的选项：

    - `-i` - 在重写一个已经存在的文件之前，提示用户确认信息

    - `-u` - 将新的文件覆盖旧的文件

    - `-v` - 显示翔实的操作信息

- rm

    rm 命令用于删除文件或目录（例如：删除文件 foo 和 bar）

    ```bash
    tony@pc:~$ rm foo bar
    ```

    使用 `-r` 选项递归地删除目录及其中的文件（例如：删除 dconf 目录下的所有文件和目录）

    ```bash
    tony@pc:~$ rm -r donf
    ```

    使用 `-i` 选项给予用户提示信息（例如：提示用户是否删除文件 foo）

    ```bash
    tony@pc:~$ rm -i foo
    rm: remove regular file 'foo'? y
    ```

    使用 `-f` 选项忽视不存在的文件，不显示提示信息

    ```bash
    tony@pc:~$ rm -f foo
    ```

    使用 `-v` 选项显示翔实的命令操作信息

    ```bash
    tony@pc:~$ rm -rv conf
    removed 'conf/foo'
    removed 'conf/bar'
    removed directory 'conf/'
    ```

- ln

    ln 命令用于创建链接（硬链接、软链接，软链接也被称为符号链接）

    ```bash
    tony@pc:~$ ln foo foo.hard-link
    ```

    ln 命令默认创建的是硬链接，如果要创建符号链接需要加上 `-s` 选项

    ```bash
    tony@pc:~$ ln -s foo foo.sym-link
    ```

    关于链接的说明：

    - 硬链接只能链接文件而不能链接目录，而符号链接既可以链接文件又可以链接目录

    - 当删除源文件时，符号链接会实效，而硬链接不会实效

    - 如果要让符号链接能在系统的各个目录下都有效，则使用绝对路径来创建符号链接

        ```bash
        tony@pc:~$ ln -s ~/foo foo.sym
        ```

## “过滤器”

- sort

    sort 命令用于排列文本行

    ```bash
    tony@pc:~$ ls ~ | sort -r | less
    ```

- uniq

    uniq 命令用于去除文本行中的重复行

    ```bash
    tony@pc:~$ ls /bin /usr/bin | sort | uniq | less
    ```

- grep

    grep 命令用于获取匹配项

    ```bash
    tony@pc:~$ ls /bin /usr/bin | sort | uniq | grep zip | less
    ```

- tee

    tee 命令从标准输入读取内容，将内容写入标准输出或文件

    ```bash
    tony@pc:~$ ls -l /usr/bin | tee output | less
    ```

## 其他

- clear

    clear 命令用于清空屏幕

- history

    history 命令用于显示命令历史

- echo

    echo 命令用于输出参数字符串

- printenv

    printenv 命令用于查看环境变量

- sleep

    sleep 命令用于延时执行命令