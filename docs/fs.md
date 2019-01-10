# Navigate the file system

## pwd

> pwd (1) - print name of current/working directory

print the current directory

```
user@pc ~ $ pwd
/home/tony
```

## ls

> ls (1) - list directory contents

list current directory files and directories

```
user@pc ~ $ ls
Desktop   Documents
```

list all files and directories

```
user@pc ~ $ ls -alF
```

list the `/home/user` and `~/repos` all files and directories

```
user@pc ~ $ ls /home/user ~/repos
/home/user:
Desktop   Document  repos

/home/user/repos:
common-linux-cmd
```

## cd

> cd (built-in) - change directory

`$ cd [PATHNAME]` will change the directory to the [PATHNAME].

[PATHNAME] can be absolute pathname or relative pathname.

change the directory to the `repos`

```
user@pc ~ $ cd repos
```

### absolute pathname

An absolute pathname begins with the root directory.

Examples: `/usr/bin`, `/home/user`

### relative pathname

There are two special symbols in relative pathname.

- `.` - refers to the working directory

- `..` - refers to the working directory's parent directory

## file

> file (1) - determine file type

Unix like OS: "Everything is file."

display the `hello.c` file type

```
user@pc ~ $ file hello.c
hello.c: C source, ASCII text
```

## less

> less (1) - opposite of more

view text file content

```
user@pc ~ $ less foo
Hello, Linux!
```

The most common used commands in less

| Command                | Action                                                        |
| ---------------------- | ------------------------------------------------------------- |
| [Page Up] or b         | Scroll back one page                                          |
| [Page Down] or [Space] | Scroll forward one page                                       |
| [Up Arrow] or k        | Scroll up one line                                            |
| [Down Arrow] or j      | Scroll down one line                                          |
| G                      | Move to the end of the text file                              |
| g                      | Move to the beginning of the text file                        |
| /characters            | Search forward for the next occurrence of characters          |
| n                      | Search forward for the next occurrence of the previous search |
| h                      | Display help screen                                           |
| q                      | Quit less                                                     |
