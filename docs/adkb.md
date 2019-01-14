# Advanced keyboard operation

bash uses a library (a shared collection of routines that different programs can use) called Readline to implement command line editing.

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

| Key        | Action                                                          |
| ---------- | --------------------------------------------------------------- |
| [Ctrl + k] | Kill text from the cursor location to **the end of line**       |
| [Ctrl + u] | Kill text from the cursor location to **the beginning of line** |
