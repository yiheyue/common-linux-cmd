# 压缩 归档

## 压缩

- gzip / gunzip

    gzip 命令用于压缩文件；gunzip 命令用于恢复被压缩的文件

    使用 `-v` 选项显示详细信息

    ```bash
    tony@pc:~$ gzip -v foo.txt
    foo.txt:	 58.5% -- replaced with foo.txt.gz
    ```

    使用 `-d` 解压缩

    ```bash
    tony@pc:~$ gzip -d foo.txt.gz
    ```

    或者使用 gunzip 命令解压缩

    ```bash
    tony@pc:~$ gunzip foo.txt.gz
    ```

    仅仅查看压缩文件的内容

    ```bash
    # 使用 -c 选项
    tony@pc:~$ gunzip -c foo.txt.gz | less

    # 使用 zcat 命令
    tony@pc:~$ zcat foo.txt.gz | less

    # 使用 zcat 和 zless 命令
    tony@pc:~$ gzcat foo.txt.gz | zless
    ```

- bzip2 / bunzip2

    这两个命令类似于 gzip / gunzip。bzip2 命令用于压缩文件；bunzip2 命令用于恢复被压缩的文件

    压缩文件

    ```bash
    tony@pc:~$ bzip2 -v foo.txt
      foo.txt:  2.304:1,  3.473 bits/byte, 56.59% saved, 18024 in, 7824 out.
    ```

    解压缩文件

    ```bash
    tony@pc:~$ bunzip2 -v foo.txt.bz2
      foo.txt.bz2: done
    ```

## 归档