# Vim Cheatsheet

## Table of Contents
* [modes](#modes)
* [motions](#motions)
* [editing](#editing)
* [highlighting](#highlighting)
* [copying/cutting/pasting](#copyingcuttingpasting)
* [exiting](#exiting)
* [text objects](#text-objects)
* [search/replace](#searchreplace)
* [command](#command)
* [tabs/windows](#tabswindows)
* [marks](#marks)
* [special marks](#special-marks)
* [jump list](#jump-list)
* [change list](#change-list)
* [registers](#registers)
* [resources](#resources)

## modes

| mode        | purpose
| ---         | ---
| normal mode | navigate the structure of the file
| insert mode | edit the file
| visual mode | highlight portions of the file to manipulate at once
| ex mode     | command mode

## motions

#### Note: most motions can be repeated a number of times by prepending the number before the motions.

| command         | action
| ---             | ---
| `h`             | move cursor left
| `j`             | move cursor down
| `k`             | move cursor up
| `l`             | move cursor right
|                 |
|                 |
| `w`             | to next start of words/punctuations
| `W`             | to next start of words
| `b`             | to previous start of words/punctuations
| `B`             | to previous start of words
| `e`             | to next end of words/punctuations
| `E`             | to next end of words
| `ge`            | to previous end of words/punctuations
| `gE`            | to previous end of words
| `$`             | to end of line
| `0`             | to start of line
| `^`             | to first non-blank character of line
|                 |
|                 |
| `<C-b>`        | scroll down a page
| `<C-f>`        | scroll up a page
| `<C-d>`        | scroll down half a page
| `<C-u>`        | scroll up half a page
| `<C-e>`        | scroll down
| `<C-y>`        | scroll up
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
| `(`             | to previous sentence
| `)`             | to next sentence
| `{`             | to previous paragraph
| `}`             | to next paragraph
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

| command          | action
| ---              | ---
| `v`              | start visual mode, move cursor to highlight
| `V`              | start linewise visual mode, move cursor to highlight
| `<C-v>`          | start visual block mode, move cursor to highlight
| `v[motion]`      | start visual mode, highlight according to motion
| `v[text object]` | start visual mode, highlight according to text object
| `gv`             | reselect
| `Esc`            | exit visual mode
| `O`              | move to corner of block
| `o`              | move to other end of marked area

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
| `<C-r> 0`    | (insert mode) insert last yanked text

## exiting

| command | action
| ---     | ---
| `:w`    | write (save) file
| `:wq`   | write (save) file and quit
| `:q`    | quit (failes if changes present)
| `:q!`   | quit without saving
| `:wqa`  | write (save) and quit all open tabs

## text objects

##### Structure of editing commands: `<number><command><text object or motion>`
##### a[object] includes surrounding white space of the object
##### i[object] does not include surrounding white space of the object

| command      | action
| ---          | ---
| `aw`         | a word
| `iw`         | inner word
| `as`         | a sentence (ends with a period)
| `is`         | inner sentence (ends with a period)
| `ap`         | a paragraph (ends with a blank line)
| `ip`         | inner paragraph (ends with a blank line)
| `a"`         | a double quoted string
| `i"`         | inner double quoted string
| `a'`         | a single quoted string
| `i'`         | inner single quoted string
| ``a` ``      | a back quoted string
| ``i` ``      | inner back quoted string
| `at`         | a single tag
| `it`         | inner single tag
|              |
|              |
| `a(` or `a)` | a parenthesized block
| `i(` or `i)` | inner parenthesized block
| `a[` or `a]` | a bracketed block
| `i[` or `i]` | inner bracketed block
| `a{` or `a}` | a brace block
| `i{` or `i}` | inner brace block
| `a<` or `a>` | a tag block
| `i<` or `i>` | inner tig block

| command      | action                                       | plugin
| ---          | ---                                          | ---
| `i<leader>w` | inner camel-cased word                       | bkad/CamelCaseMotion
| `aa`         | a function argument                          | vim-scripts/argtextobj.vim
| `ia`         | inner function argument                      | vim-scripts/argtextobj.vim
| `ai`         | the current indentation level and line above | michaeljsmith/vim-indent-object
| `ii`         | the current indentation level                | michaeljsmith/vim-indent-object

<money></money>

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
| `<C-w> v`    | vertially split windows
| `<C-w> s`    | horizontally split windows
| `<C-w> w`    | switch between windows
| `<C-w> q`    | quit a window
|               |
|               |
| `<C-w> h`    | switch to left window
| `<C-w> j`    | switch to down window
| `<C-w> k`    | switch to up window
| `<C-w> l`    | switch to right window

## marks

| command          | action
| ---              | ---
| `m{a-z}`         | set mark {a-z} at cursor position
| `m{A-Z}`         | set a global mark {A-Z} at cusor position, will work between files
| `\`{a-z}`        | move the cursor to the start of line where mark is set
| `:marks`         | list all the current marks
| `:marks aB`      | list marks a, B
|                  |
|                  |
| `]'`             | jump to next line with a lowercase mark
| `['`             | jump to previous line with a lowercase mark
| ``]` ``          | jump to next lowercase mark
| ``[` ``          | jump to previous lowercase mark
|                  |
|                  |
| `:delmarks a`    | delete mark a
| `:delmarks a-d`  | delete mark a, b, c, d
| `:delmarks abxy` | delete mark a, b, x, y
| `:delmarks aA`   | delete mark a, A
| `:delmarks!`     | delete all lowercase marks for the current buffer (a-z)

## special marks

| command              | action
| ---                  | ---
| `` `. `` or `'.`     | jump to position where last change occurred in current buffer
| `` `" ``             | jump to position where last exited current buffer
| `` `[num] ``         | jump to position in previous n-th file edited (when exited Vim)
| `''`                 | jump back (to line in current buffer where jumped from)
| `` `` ``             | jump back (to position in current buffer where jumped from)
| `` `[ `` or `` `] `` | jump to beginning/end of previously changed or yanked text
| `` `< `` or `` `> `` | jump to beginning/end of last visual selection

## jump list

| command  | action
| ---      | ---
| `<C-o>` | go backward in jump list
| `<C-i>` | go forward in jump list
| `:jumps` | display jump list

## change list

| command    | action
| ---        | ---
| `g;`       | go backward in change list
| `g,`       | go forward in change list
| `:changes` | display change list

## registers

| command      | action
| ---          | ---
| `:reg`       | display registers
| `:reg a b c` | display a, b, c registers
| `"ry"`       | yank to register r
| `"rp"`       | paste from register r
| `<C-r> r`   | in insert/command mode, paste from register r
|              |
|              |
| `".`         | last inserted text
| `"%`         | current file path
| `":`         | most recently executed command
| `"=`         | expression register
| `<C-r> =`   | open expression prompt. Ex: type 2+2 <enter>, a 4 will be printed

## misc commands

| command     | action
| ---         |
| `q:`        | display command window
| `:source %` | source vimrc file
| `:g/[pattern]/[command]` | apply ex command to every line where the regex pattern matches.

## resources

[A Great Vim Cheat Sheet](http://vimsheet.com)

[Advanced Vim Cheat Sheet](http://vimsheet.com/advanced.html)

[Vim Text Objects: The Dfinitive Guide](https://blog.carbonfive.com/2011/10/17/vim-text-objects-the-definitive-guide/)

[nicknisi/vim-workshop](https://github.com/nicknisi/vim-workshop/blob/master/vim-workshop.pdf)

[Vim Tips Wiki: Using marks](https://vim.fandom.com/wiki/Using_marks)

[Vim registers: The basics and beyond](https://www.brianstorti.com/vim-registers/)
