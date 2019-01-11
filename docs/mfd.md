# Manipulate files and directories

The shell provides special characters to help us rapidly specify groups of filenames. These special characters are called wildcards.

Wildcards

| Wildcard      | Meaning                                                          |
| ------------- | ---------------------------------------------------------------- |
| *             | Matches any characters                                           |
| ?             | Matches any single character                                     |
| [characters]  | Matches any character that is a member of the set characters     |
| [!characters] | Matches any character that is not a member of the set characters |
| [[:alnum:]]   | Matches any alphanumeric character                               |
| [[:alpha:]]   | Matches any alphabetic character                                 |
| [[:digit:]]   | Matches any numeral                                              |
| [[:lower:]]   | Matches any lowercase letter                                     |
| [[:upper:]]   | Matches any upper letter                                         |

Wildcards can be used with any command that accepts filenames as arguments.

## cp

> cp (1) - copy files and directories

There are two common ways to use `cp` command.

1. `cp item1 item2` - copy item1 to item2

2. `cp item... dir` - copy some items into dir

The most common used options for cp

| Option short | Option long   |
| ------------ | ------------- |
| -i           | --interactive |
| -r           | --recursive   |
| -u           | --update      |
| -v           | --verbose     |

e.g. copy foo to bar with informative messages

```
user@pc ~ $ cp -v foo bar
foo -> bar
```

e.g. copy foo to bar with a confirmation of overwriting

```
user@pc ~ $ cp -i foo bar
cp: overwrite 'bar'? y
```

## mv

> mv (1) - move (rename) files

There are two common ways to use `mv` command.

1. `mv item1 item2` - move or rename item1 to item2

2. `mv item... dir` - move some items into dir

The most common used options for mv

| Option short | Option long   |
| ------------ | ------------- |
| -i           | --interactive |
| -u           | --update      |
| -v           | --verbose     |

e.g. move foo bar into dir

```
user@pc ~ $ mv foo bar dir
```

e.g. rename foo to bar

```
user@pc ~ $ mv foo bar
```

## mkdir

> mkdir (1) - make directories

e.g. create three directories named "dist", "build", "src"

```
user@pc ~ $ mkdir dist build src
```

e.g. create two directory named "components", "NavBar" and "NavBar" inside "components"

```
user@pc ~ $ mkdir -p components/NavBar
```

## rm

> rm (1) - remove files or directories

The most common used options for rm

| Option short | Option long   |
| ------------ | ------------- |
| -i           | --interactive |
| -r           | --recursive   |
| -f           | --force       |
| -v           | --verbose     |

When we use `rm` command, add the `-i` option is recommanded.

If you add `-f` or `--force` option, it will override the `-i` or `--interactive` option.

e.g. remove foo with a confirmation of deleting

```
user@pc ~ $ rm -i foo
rm: remove regular file 'foo'? y
```

## ln

> ln (1) - make links between files

There are two types links in Linux. Hard links and symbolic links (soft link or symlink).

Hard links are the original Unix way of creating links; Symbol links are more modern.

Hard links have two important limitations:

1. A hard link cannot reference a file outside its own file system. This means a link may not reference a file that is not on the same disk partition as the link itself.

2. A hard link may not reference a directory.

e.g. create a hard link for foo

```
user@pc ~ $ ln foo foo2
```

e.g. create a symbolic link for foo

```
user@pc ~ $ ln -s foo foo2
```
