# Shell expansions and quoting

## echo

> echo (built-in) - Write arguments to the standard output

e.g. write text arguments to the stdout

```
user@pc ~ $ echo this is my pen!
this is my pen!
```

## printenv

> printenv (1) - print all or part of environment

## sleep

> sleep (1) - delay for a specified amount of time

## Expansion

The `bash` performs several processes upon the text before it carries out your command. For example "*", "*" have a lot of meaning to the shell. The process that makes this happen is called expansion.

e.g. expansion with "*"

```
user@pc ~ $ echo *
Desktop Document repos ...
```

### Pathname expansion

e.g. list hidden files

```
user@pc ~ $ ls .[!.]?*
```

### Tilder character expansion

The `~` character refers to user home directory pathname.

e.g. display the user home directory

```
user@pc ~ $ echo ~
/home/user
```

### Arithmetic expression expansion

Arithmetic expression expansion form: `$((expression))`, the operands of expression only support integer.

e.g. calculate 2 + 2

```
user@pc ~ $ echo $((2 + 2))
```

Arithmetic Operators

| Operator | Description    |
| -------- | -------------- |
| +        | Addition       |
| -        | Subtraction    |
| *        | Multiplication |
| /        | Division       |
| %        | Module         |
| **       | Exponentiation |

e.g. calculate 5 ^ 2 + 3

```
user@pc ~ $ echo $(((5 ** 2) + 3))
28
```

### Brace expansion

We can create multi-text strings with `{}`.

e.g. create some ordered text strings

```
user@pc ~ $ echo pre-{AA,BB,CC}-post
pre-AA-post pre-BB-post pre-CC-post

user@pc ~ $ echo pre-{0..5}
pre-0 pre-1 pre-2 pre-3 pre-4 pre-5

user@pc ~ $ echo {z..s}-post
z-post y-post x-post w-post v-post u-post t-post s-post
```

### Parameter expansion

e.g. display `USER` value

```
user@pc ~ $ echo $USER
user
```

e.g. display all available variables

```
user@pc ~ $ printenv | less
```

### Command substitution

Command substitution allows us to use the output of a command as an expansion

e.g. list `cp` in long format

```
user@pc ~ $ ls -l $(which cp)
-rwxr-xr-x 1 root root 153756 Mar  2  2017 /bin/cp
```

e.g. list `cp` in long format (old version)

```
user@pc ~ $ ls -l `which cp`
-rwxr-xr-x 1 root root 153756 Mar  2  2017 /bin/cp
```

e.g. use pipeline and command substitution

```
user@pc ~ $ file $(ls /usr/bin/* | grep zip)
...
...
```

### Quoting

The shell provides a mechanism called quoting to selectively suppress unwanted expansions.

#### Double quotes

If you place text inside double quotes, all the special characters used by the shell lose their special meaning and are treated as ordinary characters.

The exceptions are `$`, `\` (backslash), and \` (back-quote).

e.g. output the multi-space

```
user@pc ~ $ echo "hahaha     bye"
hahaha    bye
```

There is a difference between `echo $(cal)` and `echo "$(cal)"`. The first command has 38 arguments, the second one has only one.

#### Single quotes

If we need to suppress all expansions, we use single quotes.

e.g. test the single quotes

```
user@pc ~ $ echo '* ~ $USER {a,b}'
* ~ $USER {a,b}
```

### Escape character

It is common to use to selectively prevent an expansion.

e.g. prevent an expansion

```
user@pc ~ $ echo "User $USER balance: \$5.00"
User user balance: $5.00
```

It is also common to use escaping to eliminate the special meaning of a character in a filename.

e.g. usage in filename

```
user@pc ~ $ mv bad\$filename good_filename
```

The backslash loses its special meaning and is treated as an ordinary character.

e.g. a simple demo

```
user@pc ~ $ sleep 10; echo -e "Time's up\a"

user@pc ~ $ sleep 10; echo "Time's up"$'\a'
```
