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

## cd

> cd - bash built-in command

`$ cd [PATHNAME]` will change the directory to the [PATHNAME].

[PATHNAME] can be absolute pathname or relative pathname.

```
user@pc ~ $ ls -alF
```

### absolute pathname

An absolute pathname begins with the root directory.

Examples: `/usr/bin`, `/home/user`

### relative pathname

There are two special symbols in relative pathname.

- `.` - refers to the working directory

- `..` - refers to the working directory's parent directory
