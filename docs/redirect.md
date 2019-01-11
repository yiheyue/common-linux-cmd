# I/O redirection

Standard input, standard output, standard error:

- standard input (stdin) - program input

- standard output (stdout) - the data the program is designed to produce

- standard error (stderr) - status and error messages of program

By default, stdout and stderr are linked to the screen and not saved into a disk file.

In addition, many programs take input from stdin which is, by default, attached to the keyboard.

I/O redirection allows us to change where output goes and where input comes from. Normally, output goes to the screen and input comes from the keyboard, but with I/O redirection, we can change that.

> Redirection operator `>`, it can redirect the output to a file. It always rewritten from the beginning.

e.g. redirect the `ls` output content to `ls.output` file

```
user@pc ~ $ ls -l > ls.output
```

e.g. overwrite or clean the `ls.output` file

```
user@pc ~ $ ls -l /abc/def > ls.output
ls: cannot access '/abc/def': No such file or directory

user@pc ~ $ > ls.output
```

Simply using the redirection operator with no command preceding it will truncate an existing file or create a new, empty file.

> Redirection operator `>>`, it also can redirect the output. And it append redirected output to a file.

e.g. append redirected output to the `ls.output` file

```
user@pc ~ $ ls -l >> ls.output
```

> Redirect standard error should use the file descriptor. stdin - 0, stdout - 1, stderr - 2.

e.g. redirect the error message to the `ls.err` file

```
user@pc ~ $ ls /abc/def 2> ls.err
```

> Redirect all of the output messages

e.g. the traditional way

```
user@pc ~ $ ls -l /usr/bin > ls.output 2>&1
```

e.g. the modern way

```
user@pc ~ $ ls -l /usr/bin &> ls.output
```

> Redirect to the /dev/null

e.g.

```
user@pc ~ $ ls -l /abc/def 2> /dev/null
```

## cat

> cat (1) - concatenate files and print on the standard output

`cat` command can do many things:

- display the content of a simply text file

  ```
  user@pc ~ $ cat simfile
  Hello world!
  ```

- join files together

  ```
  user@pc ~ $ cat movie.0* > movie
  ```

- read from standard input

  ```
  user@pc ~ $ cat
  How are you?
  How are you?
  ```

- create a file

  ```
  user@pc ~ $ cat > hello
  How are you?
  [Ctrl + d]
  user@pc ~ $
  ```

> Redirection operator `<`

e.g. redirect the standard input

```
user@pc ~ $ cat < hello
How are you?
```

## Pipelines

Using pipelines, the standard output of one command can be piped into the standard input of another.

`command1 | command2` - send the stdout of command1 to the stdin of the command2

e.g. `less` command can receive content from stdin

```
user@pc ~ $ ls -l /usr/bin | less
```

## Filters

Using filters to perform complex operations on data.

## sort

> sort (1) - sort lines of text files

e.g. sort the output

```
user@pc ~ $ ls /bin /usr/bin | sort | less
```

## uniq

> uniq (1) - report or omit repeated lines

e.g. remove any duplicates

```
user@pc ~ $ ls /bin /usr/bin | sort | uniq | less
```

e.g. display the duplicates

```
user@pc ~ $ ls /bin /usr/bin | sort | uniq -d | less
```

## wc

> wc (1) - print newline, word, and byte counts for each file

e.g. get the line, word and byte counts for `foo` file

```
user@pc ~ $ wc foo
 3 7 34 foo
```

e.g. display the line counts

```
user@pc ~ $ ls -l /bin /usr/bin | sort | uniq | wc -l
1876
```

## grep

> grep (1) - print lines matching a pattern

e.g. display the line that had the word "zip"

```
user@pc ~ $ ls /bin /usr/bin | sort | uniq | grep zip
bunzip2
bzip2
...
...
```

## head / tail

> head (1) - output the first part of files

> tail (1) - output the last part of files

e.g. display the first 10 lines of `passwd` file

```
user@pc ~ $ head /etc/passwd
...
...
```

e.g. display the first 5 lines of `passwd` file

```
user@pc ~ $ head -n 5 /etc/passwd
```

e.g. view file in real-time, press [Ctrl + c] to end it

```
user@pc ~ $ head -f /var/log/message
```

## tee

> tee (1) - read from standard input and write to standard output and files

e.g. catch the output content before `grep` command works

```
user@pc ~ $ ls /bin /usr/bin | tee ls.output | grep zip
```
