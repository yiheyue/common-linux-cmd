# About commands

A command can be one of four different types:

1. An executable program

2. A command built into the shell itself (shell builtin)

3. A shell function

4. An alias

## type

> type (built-in) - display the kind of a command

This command can display the kind of command.

display the kind of these commands

```
user@pc ~ $ type type
type is a shell builtin

user@pc ~ $ type ll
ll is aliased to `ls -alF'

user@pc ~ $ type cp
cp is hashed (/usr/cp)
```

## which

> which (1) - locate a command

Sometimes there is more than one version of an executable program installed on a system. While this is not very common on desktop systems, it’s not unusual on large servers.

The `which` command can determine the exact location of a given executable program.

get the exact location of these commands

```
user@pc ~ $ which which
/usr/bin/which

user@pc ~ $ which tree
/usr/bin/tree
```

## help

> help (built-in) - display the documentation of a built-in

The `help` command can get the documentation of the built-in commands.

display the documentation of `cd`

```
user@pc ~ $ help cd
cd: cd [-L|[-P [-e]] [-@]] [dir]
...
...
```

- `--help` option - many executable programs support this option to display the common usage

## man

> man (1) - an interface to the on-line reference manuals

For most executable programs, you can get their documentations from `man` command.

display the documentation of `man`

```
user@pc ~ $ man man
```

Man page organization

| Section | Content                                                  |
| ------- | -------------------------------------------------------- |
| 1       | Executable programs or shell commands                    |
| 2       | System calls (functions provided by the kernel)          |
| 3       | Library calls (functions within program libraries)       |
| 4       | Special files (usually found in /dev)                    |
| 5       | File formats and conventions e.g. /etc/passwd            |
| 6       | Games                                                    |
| 7       | Miscellaneous (including macro packages and conventions) |
| 8       | System administration commands (usually only for root)   |
| 9       | Kernel routines [Non standard]                           |

## apropos

> apropos (1) - search the manual page names and descriptions

Use `apropos` command can match the exact command that you search.

Its function is the same as `man -k command`.

match `aprop`

```
user@pc ~ $ apropos aprop
apropos (1) - search the manual page names and descriptions
```

## whatis

> whatis (1) - display one-line manual page descriptions

display the simple description about `whatis`

```
user@pc ~ $ whatis whatis
whatis (1) - display one-line manual page descriptions
```

## whereis

> whereis (1) - locate the binary, source, and manual page files for a command

locate the binary, source, and manual page files of `tree`

```
user@pc ~ $ whereis tree
tree: /usr/bin/tree /usr/share/man/man1/tree.1.gz
```

## info

> info (1) - read Info documents

The GNU Project provides an alternative to man pages for their programs, called "info".

`info` commands

| Command                  | Action                                                                      |
| ------------------------ | --------------------------------------------------------------------------- |
| ?                        | Display command help                                                        |
| [Page Up] or [Backspace] | Display privious page                                                       |
| [Page Down] or [Space]   | Display next page                                                           |
| n                        | Next - Display the next node                                                |
| p                        | Previous - Display the previous node                                        |
| u                        | Up - Display the parent node of the currently displayed node usually a menu |
| [Enter]                  | Follow the hyperlink at the cursor location                                 |
| q                        | Quit                                                                        |

display a menu page with hyperlinks to each program contained in the coreutils package

```
user@pc ~ $ info coreutils
```

## alias

> alias (built-in) - Define or display aliases

create an alias for a list of commands

```
user@pc ~ $ alias foo='cd /usr; ls; cd -'
```

> unalias (built-in) - Remove each NAME from the list of defined aliases

remove an alias

```
user@pc ~ $ unalias foo
```
