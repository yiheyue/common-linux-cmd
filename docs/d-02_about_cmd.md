# 命令详解

## 命令

命令的形式分为以下四种：

- 一个可执行程序，例如位于 `/usr/bin` 目录中的可执行程序。这一类程序可以是用 C 或 C++ 语言写成的程序所编译成的二进制文件，也可以是由 shell，perl，python，ruby 等脚本语言写成的程序。

- 一个 shell 内建的命令（被称为 builtins）。例如，cd 命令。

- 一个 shell 函数

- 一个命令别名

## 识别命令

- type

    type 命令用于显示命令的类型

    ```bash
    tony@pc:~$ type type
    type is a shell builtin
    tony@pc:~$ type cd
    cd is a shell builtin
    tony@pc:~$ type cp
    cp is hashed (/bin/cp)
    tony@pc:~$ type ping
    ping is /bin/ping
    ```

- which

    which 命令用于显示可执行程序的位置

    ```bash
    tony@pc:~$ which which
    /usr/bin/which
    ```

- whatis

    whatis 命令用于显示可执行程序的简单描述（用途）

    ```bash
    tony@pc:~$ whatis whatis
    whatis (1)           - display one-line manual page descriptions
    ```

- whereis

    whereis 命令用于显示可执行程序的二进制文件、源码以及文档的位置

    ```bash
    tony@pc:~$ whereis whereis
    whereis: /usr/bin/whereis /usr/share/man/man1/whereis.1.gz
    ```

## 查看命令文档

大部分软件都自带了文档文件，这些文件位于 `/usr/share/doc` 目录中。

- help

    help 命名用于显示 shell 内建命令的帮助文档

    ```bash
    tony@pc:~$ help help
    help: help [-dms] [pattern ...]
        Display information about builtin commands.
    ...
    ```

- man

    man 命令用于显示某个可执行程序的详细文档

    ```bash
    tony@pc:~$ man man
    ...
    ```

    由于 Linux 上的命令众多，为了便于管理，man 将命令的文档做了分节处理

    | 章节 | 内容 |
    | - | ------------ |
    | 1 | 用户命令      |
    | 2 | 系统调用      |
    | 3 | C 库函数调用  |
    | 4 | 特殊文件      |
    | 5 | 文件格式      |
    | 6 | 游戏         |
    | 7 | 其他         |
    | 8 | 系统管理员命令 |

    因此我们可以利用章节号来查找指定命令的文档

    ```bash
    tony@pc:~$ man 5 passwd
    ```

- apropos

    apropos 命令用于模糊查找（这个命令等同于 `man -k`）

    ```bash
    tony@pc:~$ apropos printf
    asprintf (3)         - print to allocated string
    dprintf (3)          - formatted output conversion
    fprintf (3)          - formatted output conversion
    fwprintf (3)         - formatted wide-character output conversion
    printf (1)           - format and print data
    printf (3)           - formatted output conversion
    ...
    ```

- info

    info 命令用于查看命令的帮助文档

    ```bash
    tony@pc:~$ info cp
    ...
    ```

## 命令别名

我们可以使用 `;` 来分隔命令，使它们一个接一个的执行，例如：

```bash
tony@pc:~$ cd /; ls -l; cd -
```

同样的，我们可以为上述的命令集取一个别名 foo：

```bash
tony@pc:~$ alias foo='cd /; ls -l; cd -'
```

当我们执行 foo 时，等同于执行 `cd /; ls -l; cd -`。

alias 命令相关：

- 查看所有的命令别名

    ```bash
    tony@pc:~$ alias
    alias alert='notify-send --urgency=low -i "$([ $? = 0 ] && echo terminal || echo error)" "$(history|tail -n1|sed -e '\''s/^\s*[0-9]\+\s*//;s/[;&|]\s*alert$//'\'')"'
    alias egrep='egrep --color=auto'
    alias fgrep='fgrep --color=auto'
    ...
    ```

- 删除命令别名

    ```bash
    tony@pc:~$ unalias foo
    ```