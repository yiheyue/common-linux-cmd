# 权限

## 权限属性

| 权限属性 | 文件                  | 目录                          |
| ------- | -------------------- | ---------------------------- |
| r       | 允许打开并读取文件内容   | 允许列出目录中的内容            |
| w       | 允许写入文件           | 允许在目录下新建、删除或重命名文件 |
| x       | 允许将文件作为程序来执行 | 允许进入目录                   |

- id

    id 命令用于显示用户的 UID 和 GID

    ```bash
    tony@pc:~$ id
    uid=1000(tony) gid=1000(tony) groups=1000(tony)
    ...
    ```

- chmod

    chmod 命令用于更改文件模式（权限），该命令有两种使用方式：

    - 八进制数字法

        八进制与文件模式映射表

        | 八进制 | 二进制 | 文件模式 |
        | ----- | ----- | ------- |
        | 0     | 000   | ---     |
        | 1     | 001   | --x     |
        | 2     | 010   | -w-     |
        | 3     | 011   | -wx     |
        | 4     | 100   | r--     |
        | 5     | 101   | r-x     |
        | 6     | 110   | rw-     |
        | 7     | 111   | rwx     |

        给文件 foo 设置 `rw-r--r--` 权限

        ```bash
        tony@pc:~$ chmod 644 foo
        ```

    - 符号表示法

        符号与其对应的描述

        | 符号 | 描述 |
        | --- | --- |
        | u   | 即 user，意思是文件或目录的所有者 |
        | g   | 即 group，意思是用户组          |
        | o   | 即 others，意思是其他人         |
        | a   | 即 all，意思是 u g o 三者的联合  |

        给文件的 u 和 o 添加 x 权限

        ```bash
        tony@pc:~$ chmod uo+x foo
        ```

- umask

    umask 命令用于设置文件模式掩码（即设置默认权限）

    原始文件模式：`--- rw- rw- rw-`

    默认掩码：`000 000 000 010`

    结果：`--- rw- rw- r--`

- su

    su 命令用于改变用户 ID 或成为超级用户

    ```bash
    tony@pc:~$ su -
    Password: 
    root@pc:~# pwd
    /root
    ```

    退出超级用户

    ```bash
    root@pc:~# exit
    logout
    ```

- sudo

    sudo 命令可以让普通用户使用超级用户的权限执行一条命令

- chown

    chown 命令用于改变文件的所有者和用户组（例如，将 test_file 文件的所有者和用户组改为 mike）

    ```bash
    tony@pc:~$ sudo chown mike: test_file
    ```

- chgrp

    chgrp 命令也可以改变文件的用户组（例如，将 test_file 文件的用户组改为 mike）

    ```bash
    tony@pc:~$ sudo chgrp mike test_file
    ```

- passwd

    passwd 命令用于改变用户的密码（例如，修改 mike 用户的密码）

    ```bash
    tony@pc:~$ sudo passwd mike
    ```

关于管理用户和用户组的命令：

- adduser

- addgroup

- deluser

- useradd

- userdel

- usermod

- groupadd

- groupdel

- groupmod