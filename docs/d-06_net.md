# 网络相关

- ping

    ping 命令用来发送一个 ICMP ECHO_REQUEST 数据包

    ```bash
    tony@pc:~$ ping baidu.com
    PING baidu.com (220.181.57.216) 56(84) bytes of data.
    64 bytes from 220.181.57.216 (220.181.57.216): icmp_seq=1 ttl=48 time=85.6 ms
    64 bytes from 220.181.57.216 (220.181.57.216): icmp_seq=2 ttl=48 time=120 ms
    ...
    ```

- traceroute/tracepath

    这两个命令用于显示本地到主机需要经过的路由器跳数

    ```bash
    tony@pc:~$ tracepath baidu.com
     1?: [LOCALHOST]                      pmtu 1500
     1:  _gateway                                              7.470ms 
     1:  _gateway                                              3.871ms 
     2:  _gateway                                             11.904ms pmtu 1400
    ...
    ```

- netstat

    netstat 命令可以被用来处理各种网络问题

- ftp

    ftp 命令可以用来下载远程主机上的文件

- lftp

    ftp 命令的改进版

- wget

    wget 命令也可以下载文件

- ssh

    ssh 命令是 OpenSSH 的客户端程序

- scp

    scp 即 secure copy，用于复制远程主机的文件

- sftp

    sftp 即 secure ftp，通过加密的方式使得文件传输更加安全