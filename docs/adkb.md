# Advanced keyboard operation

bash uses a library (a shared collection of routines that different programs can use) called Readline to implement command line editing.

## clear

> clear (1) - clear the terminal screen

e.g. clear the terminal screen

```
user@pc ~ $ clear
```

## history

> history (3readline) - GNU History Library

## script

> script (1) - make typescript of terminal session

## Move the cursor

The following table lists the keys used to move the cursor.

Cursor movement commands

| Key        | Direction | Action                                       |
| ---------- | --------- | -------------------------------------------- |
| [Ctrl + a] | <------   | Move cursor to the **beginning of the line** |
| [Ctrl + e] |   ------> | Move cursor to the **end of the line**       |
| [Ctrl + f] |        -> | Move cursor **forward one character**        |
| [Ctrl + b] | <-        | Move cursor **backward one character**       |
| [Alt + f]  |      ---> | Move cursor **forward one word**             |
| [Alt + b]  | <---      | Move cursor **backward one word**            |
| [Ctrl + l] |           | Clear the screen                             |

## Edit text

Text editing commands

| Key        | Action                                                                              |
| ---------- | ----------------------------------------------------------------------------------- |
| [Ctrl + d] | Delete the character at the cursor location                                         |
| [Ctrl + t] | Exchange the character at the cursor location with the one preceding it             |
| [Alt + t]  | Exchange the word at the cursor location with the one preceding it                  |
| [Alt + l]  | Convert the characters from the cursor location to the end of the word to lowercase |
| [Alt + u]  | Convert the characters from the cursor location to the end of the word to uppercase |

## Kill and yank

The Readline documentation uses the terms killing and yanking to refer to what we would commonly call cutting and pasting. Items that are cut are stored in a buffer called the kill-ring.

Cut and paste commands

| Key               | Action                                                                |
| ----------------- | --------------------------------------------------------------------- |
| [Ctrl + k]        | Kill text from the cursor location to **the end of line**             |
| [Ctrl + u]        | Kill text from the cursor location to **the beginning of line**       |
| [Alt + d]         | Kill text from the cursor location to **the end of the current word** |
| [Alt + Backspace] | Kill text from the cursor location to **the beginning of the word**   |
| [Ctrl + y]        | Yank text from the kill-ring and insert it at the cursor location     |

## Completion

Completion occurs when user press [Tab] key.

Completion commands

| Key       | Action                               |
| --------- | ------------------------------------ |
| [Alt + ?] | Display list of possible completions |
| [Alt + *] | Insert all possible completions      |

## History commands

We can view the contents of the commands history at any time.

e.g. view the history

```
user@pc ~ $ history | less
...
...
```

e.g. search command using `grep`

```
user@pc ~ $ history | grep root
1367  su root
```

e.g. using history expansion to execute the command

```
user@pc ~ $ !1367
su root
Password:
```

### Search the history list incrementally

- type [Ctrl + r] to start incremental search

- type [Enter] to execute the command

- type [Ctrl + j] to copy this command to the current command line

- type [Ctrl + g] or [Ctrl + c] to quit searching

History commands

| Key        | Action                                                                   |
| ---------- | ------------------------------------------------------------------------ |
| [Ctrl + p] | Move to the **previous** history entry                                   |
| [Ctrl + n] | Move to the **next** history entry                                       |
| [Alt + <]  | Move to the **beginning** of history list                                |
| [Alt + >]  | Move to the **end** of history list                                      |
| [Ctrl + r] | Reverse incremental search                                               |
| [Alt + p]  | Reverse search, non-incremental                                          |
| [Alt + n]  | Forward search, non-incremental                                          |
| [Ctrl + o] | Execute the current item in the history list and advance to the next one |

History expansion commands

| Sequence | Action                                             |
| -------- | -------------------------------------------------- |
| !!       | Repeat the last command                            |
| !number  | Repeat history list item number                    |
| !string  | Repeat last history list item starting with string |
| !?string | Repeat last history list item containing string    |