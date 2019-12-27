# Vim Cheatsheets

## modes

| mode        | purpose
| ---         | ---
| normal mode | navigate the structure of the file
| insert mode | edit the file
| visual mode | highlight portions of the file to manipulate at once
| ex mode     | command mode

## movements

#### Note: commands with [count] can be prepended with a number of count to repeat the commands.

| command         | action
| ---             | ---
| `h`             | [count] move cursor left
| `j`             | [count] move cursor down
| `k`             | [count] move cursor up
| `l`             | [count] move cursor right
|                 |
|                 |
| `w`             | [count] to next start of words/punctuations
| `W`             | [count] to next start of words
| `e`             | [count] to next end of words/punctuations
| `E`             | [count] to next start of words
| `b`             | [count] to previous start of words/punctuations
| `B`             | [count] to previous start of words
| `$`             | [count] to end of line
| `0`             | to start of line
| `^`             | to first non-blank character of line
|                 |
|                 |
| `Ctrl+b`        | [count] scroll down a page
| `Ctrl+f`        | [count] scroll up a page
| `Ctrl+d`        | scroll down half a page
| `Ctrl+u`        | scroll up half a page
| `Ctrl+e`        | [count] scroll down
| `Ctrl+y`        | [count] scroll up
|                 |
|                 |
| `H`             | to top of window
| `M`             | to middle of window
| `L`             | to bottom of window
|                 |
|                 |
| `gg`            | top of file
| `G`             | bottom of file
| `:[num]<enter>` | to specified line number
|                 |
|                 |
| `(`             | [count] to previous sentence
| `)`             | [count] to next sentence
| `{`             | [count] to previous paragraph
| `}`             | [count] to next paragraph
|                 |
|                 |
| `f[char]`       | move to next char on the current line
| `F[char]`       | move to previous char on the current line
| `t[char]`       | move to before next char on the current line
| `T[char]`       | move to before previous char on the current line
| `;`             | go to next searched (f/F/t/T) character
| `,`             | go to previous searched (f/F/t/T) character

## editing

| command   | action
| ---       | ---
| `i`       | start insert mode at cursor
| `I`       | insert at start of line
| `a`       | append after the cursor
| `A`       | append at the end of line
| `o`       | open blank line below current line
| `O`       | open blank line above current line
| `Esc`     | exit insert mode
|           |
|           |
| `r[char]` | replace a single char with specified char
| `R`       | enter replace mode to replace a block of chars
|           |
|           |
| `J`       | join line below to current line

## highlighting

| command  | action
| ---      | ---
| `v`      | start visual mode, move cursor to highlight
| `V`      | start linewise visual mode, move cursor to highlight
| `Ctrl+v` | start visual block mode, move cursor to highlight
| `gv`     | reselect
| `Esc`    | exit visual mode
| `O`      | move to corner of block
| `o`      | move to other end of marked area

## copying/cutting/pasting

| command       | action
| ---           | ---
| `y`           | yank (copy) marked text
| `yy`          | yank current line
| `y[movement]` | yank to move-to point
| `d`           | delete marked text
| `dd`          | delete current line
| `d[movement]` | delete to move-to point
| `c`           | delete marked text and go into insert mode
| `cc`          | delete current line and go into insert mode
| `c[movement]` | delete to move-to point and go into insert mode
| `x`           | delete current char
| `X`           | delete previous char
| `p`           | put (paste) after cursor
| `P`           | put (paste) before cursor
|               |
|               |
| `Ctrl+r 0`    | (insert mode) insert last yanked text

## exiting

| command | action
| ---     | ---
| `:w`    | write (save) file
| `:wq`   | write (save) file and quit
| `:q`    | quit (failes if changes present)
| `:q!`   | quit without saving
| `:wqa`  | write (save) and quit all open tabs

## text objects

| command         | action
| ---             | ---

## search/replace

| command          | action
| ---              | ---
| `/pattern`       | search forward for pattern
| `?pattern`       | search backward for pattern
| `/pattern\c`     | search case-insensitive
| `/pattern\C`     | search case-sensitive
| `n`              | repeat search in same direction
| `N`              | repeat search in opposite direction
| `:%s/old/new/g`  | replace all old with new throughout file
| `:%s/old/new/gc` | replace all old with new throughout file with confirmation (better to use `gn`)
| `gn`             | jump to next search, can be used as a motion. Ex: `/search`, `cgn`, insert text, then use `.` to replace text one by one.
| `gN`             | similar to `gn`, but jumps to previous search

## tabs/windows

| command       | action
| ---           | ---
| `:e filename` | open file
| `:tabe`       | make a new tab
| `gt`          | go to next tab
| `gT`          | go to next tab
|               |
|               |
| `vsp`         | vertically split windows
| `sp`          | horizontally split windows
| `Ctrl+w v`    | vertially split windows
| `Ctrl+w s`    | horizontally split windows
| `Ctrl+w w`    | switch between windows
| `Ctrl+w q`    | quit a window
|               |
|               |
| `Ctrl+w h`    | switch to left window
| `Ctrl+w j`    | switch to down window
| `Ctrl+w k`    | switch to up window
| `Ctrl+w l`    | switch to right window

## marks

| command   | action
| ---       | ---
| `m{a-z}`  | set mark {a-z} at cursor position
| `m{A-Z}`  | set a global mark {A-Z} at cusor position, will work between files
| `\`{a-z}` | move the cursor to the start of line where mark is set

## jump list

| command  | action
| ---      | ---
| `Ctrl+o` | go backward in jump list
| `Ctrl+i` | go forward in jump list

## change list

| command | action
| ---     | ---
| `g;`    | go backward in change list
| `g,`    | go forward in change list

## registers

## credits

https://github.com/nicknisi/vim-workshop/blob/master/vim-workshop.pdf

http://vimsheet.com

http://vimsheet.com/advanced.html

https://blog.carbonfive.com/2011/10/17/vim-text-objects-the-definitive-guide/

https://vim.fandom.com/wiki/Using_marks
