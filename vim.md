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

## Basic commands

| keystroke | action
| ---       | ---
| `:help` | open vim help

## Exit/Open files

| keystroke | action
| ---       | ---
| `:q` | quit current window
| `:w` | write (save) current file
| `:wq` or `:x` | write current file and quit current window
| `:e <path>` | edit (open) file
 
- Appending `a` executes command on all files
- Appending `!` after `:q` quits without saving

Example:

| keystroke | action
| ---       | ---
| `:qa!` | quit all files/windows without saving

## Searching

Type `/` to initiate command to search, type in the text to search, and press `<Enter>` 

| keystroke | action
| ---       | ---
| `/text` | search `text`
| `n` | go to next found occurence
| `n` | go to prev found occurence
| `*` | Search forward the word under cursor
| `#` | Search backward the word under cursor

## Undo and Redo

| keystroke | action
| ---       | ---
| `u` | undo
| `<C-r>` | redo

## Insert Mode

| keystroke | action
| ---       | ---
| `i`       | insert at cursor
| `I`       | insert at start of line
| `a`       | append after the cursor
| `A`       | append at the end of line
| `o`       | open blank line below current line
| `O`       | open blank line above current line
| `Esc`     | exit insert mode

## motions

Note: most motions can be repeated a number of times by prepending the number before the motions.

Example: `6j` moves cursor down 6 rows

#### Moving

| keystroke         | action
| ---             | ---
| `h`             | move cursor left
| `j`             | move cursor down
| `k`             | move cursor up
| `l`             | move cursor right

#### Moving horizontally

| keystroke         | action
| ---             | ---
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
| `f[char]`       | move to next char on the current line
| `F[char]`       | move to previous char on the current line
| `t[char]`       | move to before next char on the current line
| `T[char]`       | move to before previous char on the current line
| `;`             | go to next searched (f/F/t/T) character
| `,`             | go to previous searched (f/F/t/T) character

#### Moving vertically

| keystroke         | action
| ---             | ---
| `gg`            | top of file
| `G`             | bottom of file
| `:[num]<enter>` | to specified line number
|                 |
| `<C-b>`        | scroll down a page
| `<C-f>`        | scroll up a page
| `<C-d>`        | scroll down half a page
| `<C-u>`        | scroll up half a page
| `<C-e>`        | scroll down
| `<C-y>`        | scroll up
|                 |
| `H`             | to top of window
| `M`             | to middle of window
| `L`             | to bottom of window
|                 |
| `(`             | to previous sentence
| `)`             | to next sentence
| `{`             | to previous paragraph
| `}`             | to next paragraph

#### Jump list

| keystroke         | action
| ---             | ---
| `<C-o>` | Go to previous cursor position
| `<C-i>` | Go to next cursor position
| `:jumps` | show jump list

#### Change list

| keystroke         | action
| ---             | ---
| `g;` | jump to the next change
| `g,` | jump to the previous change
| `:changes` | show change list

#### Method jumps

| keystroke | action
| --- | ---
| `[m` | move to start of a method
| `]m` | move to end of a method

## Operators

Opearators are actions that need to be combined with motions or text objects (see below) to work.

| keystroke         | action
| ---             | ---
| `d`            | delete
| `c`            | change (delete and go to insert mode)
| `y`            | yank (copy)

For example, `ggdG` moves to start of file and delete until end of file.

## Text objects

Text objects are commands that can only be used while in visual mode or after an operator.

The commands either start with `a`, `a`n object, or `i`, `i`nner object, followed by an objects.

| keystroke         | action
| ---             | ---
| a[object] | include surrounding [object character/white space/empty line] of the object 
| i[object] | not include surrounding [object character/white space/empty line] of the object

#### Objects

| keystroke         | action
| ---             | ---
| `w` | word 
| `s` | sentence
| `p` | paragraph
| `"` | a pair of double quote
| `'` | a pair of single quote
| `` ` `` | a pair of back quote
| `(` or `)` | parenthesized block
| `[` or `]` | parenthesized block
| `(` or `)` | parenthesized block
| `<` or `>` | tag block
| `t` | a pair of tag `<body></body>`

#### Plugin objects

Some useful objects not supported in vanilla vim.

| keystroke | action                        | plugin
| ---     | ---                           | ---
| `a`     | a function argument           | vim-scripts/argtextobj.vim
| `i`     | the current indentation level | michaeljsmith/vim-indent-object

## Vim options

| keystroke         | action
| ---             | ---
| `:set <option>` | set option
| `:set no<option>` | unset option
| `:set <option>!` | toggle option
| `:set <option>?` | return option's value
| `:set <option>=<value>` | set option to value (string or number)
| `:set <option>+=<value>` | add value for number option, append value for string option
| `:set <option>-=<value>` | subtract value for number option, delete value for string option
| `:set <option>&` | reset option to default value

## Buffers

A buffer can have 3 different states:
- active - buffer is displayed in the window
- hidden - buffer is not displayed but the file is open
- inactive - buffer not displayed in empty, not linked to any file

| keystroke         | action
| ---             | ---
| `:buffers` | show buffer list

Each line in buffer list contains:
- buffer unique ID
- buffer state (`a` for active, `h` for hidden, `<Space>` for inactive)
- buffer name, can be filepath
- Line number where cursor is

| keystroke         | action
| ---             | ---
| `:buffer <ID or Name>` | move to buffer using ID or name
| `:bnext` or `:bn` | move to next buffer
| `:bprevious` or `:bp` | move to previous buffer
| `:bfirst` or `:bf` | move to first buffer
| `:blast` or `:bl` | move to last buffer
| `<C-6` | Switch to the alternate buffer, which is indicated in buffer list with symbol `#`
| `<ID><C-6` | Switch to a specific buffer with ID `<ID>`
| |
| `:bufdo <command>` | apply a command to all buffers
| `:buffers!` or `:ls!` | open buffer list including unlisted buffer, which is indicated with synbol `u` after ID
| |
| `:badd <filename>` | add <filename> to the buffer list
| `:bdelete <ID or Name>` | delete a buffer by ID or name, can specify more than one ID or name delimited by `<Space>`
| `:1,10bdelete` | delete buffer from ID 1 to 10 included
| `%bdelete` | delete all buffers

## Windows

| keystroke         | action
| ---             | ---
| `:new` | create a new window
| `<C-w> s` | split window horizontally
| `<C-w> v` | split window vertically
| `<C-w> n` | split window horizontally and edit a new file
| `<C-w> ^` | split window horizontally and edit file in alternate buffer
| `<Buffer ID><C-w> ^` | split window horizontally and edit file in buffer ID
| |
| `<C-w> [<Arrow Keys>|h|j|k|l]` | move between windows.
| `<C-w> T` | move current window to a new tab
| `<C-w> r` | rotate window positions from left to right
| `<C-w> R` | rotate window positions from right to left
| `<C-w> x` | swap position with next window
| `<C-w> H` | move current window to the far left
| `<C-w> J` | move current window to the far bottom
| `<C-w> K` | move current window to the far top
| `<C-w> L` | move current window to the far right
| |
| `<C-w> =` | resize windows to fit the screen.
| `<C-w> -` | decrease window height
| `<C-w> +` | increase window height
| `<C-w> <` | decrease window width
| `<C-w> >` | increase window width

## Tabs

| keystroke | action
| --- | ---
| `:tabnew` or `:tabe` | open a new tab
| `:tabclose` or `:tabc` | close tab
| `:tabonly` or `:tabo` | close other tabs except current tab
| `gt` | go to next tab
| `gT` | go to previous tab

## Arglist

Argument list is a subset of buffer list, files opened with `vim` command are added automatically to argument list.
For example, running `vim file1 file2` adds `file1` and `file2` to argument list, which is also in the buffer list.

| keystroke | action
| --- | ---
| `:args` | show arglist
| `:argadd` | add file to arglist
| `:argdo <command>` | execute command on every file in arglist

| `:next` | move to next file in arglist
| `:prev` | move to previous file in arglist
| `:first` | move to first file in arglist
| `:last` | move to last file in arglist

## Key mappings

| keystroke | action
| --- | ---
| `:map` | show all mappings
| `:nmap` | mapping for normal mode
| `:imap` | mapping for insert mode
| `:xmap` | mapping for visual mode
| `:nnoremap` | mapping for normal mode (non-recursive)
| `:inoremap` | mapping for insert mode (non-recursive)
| `:xnoremap` | mapping for visual mode (non-recursive)
| `:unmap` | unmap key

Special characters in mapping:

| keyname | key
| --- | ---
| `<space>` | `Space`
| `<c-w>` | `Ctrl-w`
| `<cr>` | carriage return (Enter)

To create new mappings, leader key can be utilized. First define leader key: `:let mapleader = "<space>"`, then use leader key in mapping: `nnoremap <leader>an :next<cr>`.

## Repeat keystrokes

| keystroke | action
| --- | ---
| `.` | repeat last change
| `@:` | repeat last command executed
| `@@` | repeat last `@` command executed (useful for macro)

#### Macro

1. `q<lowercase_letter>` begins recording keystrokes in a register identified by the lowercase letter
2. all keystrokes onward are recorded
3. `q` stops recording
4. `@<lowercase_letter>` execute keystrokes you've recorded

## Command line window

| keystroke | action
| --- | ---
| `q:` | open command line history
| `q/` or `q?` | open search history
| `<C-f>` | open command line history while in command line mode


## Useful "g" commands

Need to be distributed to other sections

| keystroke | action
| --- | ---
| `gf` | edit file/URL located at the filepath under cursor
| `<C-w><C-f>` | edit file/URL located at the filepath under cursor in a new window
| `gx` | open the file/URL located at the filepath under cursor using system's default application
| `gi` | move to last insertion location and switch to insert mode
| `gv` | Start visual mode and highlight previous visual mode selection
| `gn` | highlight next search, can be used as a motion. Ex: `/search`, `cgn`, insert text, then use `.` to replace text one by one
| `gN` | similar to `gn`, but jumps to previous search
| `gI` | insert text at beginning of line
| `gu` | lowercase using a motion
| `gU` | uppercase using a motion

## Ranges

| keystroke | action
| --- | ---
| `.` | current line
| `$` | last line of current buffer
| `%` | entire file (same as `1,$`)
| `*` | last visual mode selection
| `'<` | first line selected in visual mode
| `'>` | last line selected in visual mode

Examples:
| keystroke | action
| --- | ---
| `:1,40d` | delete line 1 to 40
| `:2,$d` | delete line 2 to end of file
| `:.,$d` | delete current line to end of line
| `:%d` | delete every line
| `:'<,$d` | delete first line selected in visual mode to end of file

## Quickfix lists

Commands such as `:vimgrep`, `:make`, `:grep` populate the quickfix list automatically

| keystroke | action
| --- | ---
| `:clist` or `:cl` | show quickfix list, can be used with a range as argument
| `:copen` or `:cope` | open a window (with a special buffer) to show the quickfix list
| `:cc <number>` | move to nth entry of quickfix list
| `:cnext` or `:cn` | move to next entry of quickfix list
| `:cprevious` or `:cp` | move to previous entry of quickfix list
| `:cfirst` or `:cfir` | move to first entry of quickfix list
| `:clast` or `:clas` | move to last entry of quickfix list
| `:cdo <command>` | execute command on each entry of quickfix list
| `:cexpr <expr>` or `:cex <expr>` | create quickfix list using expression result
| `:caddexpr <expr>` or `:cadde <expr>` | append result of expression result to quickfix list

Examples:

| keystroke | action
| --- | ---
| `:cex []` | empty quickfix list
| `:cex system("ls")` | populate quickfix list with shell command `ls`

## Location lists

Location list is similar to quickfix list, except location list is global and quickfix list is local to a window.

Commands such as `:lvimgrep`, `:lmake` populate location list automatically.

Location lists commands are similar to quickfix list commands, by replacing the initial `c` to `l`.

| keystroke | action
| --- | ---
| `:llist` or `:lli` | show location list, can be used with a range as argument
| `:ll <number>` | move to nth entry of location list
| `:lnext` or `:lne` | move to next entry of location list

and so on...

## Registers

| keystroke | action
| --- | ---
| `:registers` or `:reg` | show contents of registers
| `"<reg>` | specifies the register to be read or written

Examples:

| keystroke | action
| --- | ---
| `"add` | delete line and store content in register `a`
| `"ap` | paste content in register `a`

#### Types of registers

1. The unnamed register (`"`) - contains last deleted/changed/yanked content even if one register was specified.
2. The numbered registers(from `0` to `9`)
  - `0` contains content of last yank
  - `1` to `9` is a stack containing content deleted or changed
3. The small delete register (`-`) - contains any deleted or changed content smaller than one line, not written if register `"` is specified.
4. The named registers (`a` to `z`)
  - vim will not write to them if not specified with keystroke `"`
  - Use uppercase name of each register to append to it
5. The read only registers(`.`, `%` and `:`)
  - `.` contains last inserted text
  - `%` contains the name of current file
  - `:` contains most recent command line executed
6. The alternate buffer register (`#`) - contains alternate buffer for current window.
7. The expression register (`=`) - stores result of an expression.
8. The selection register (`+` and `*`)
  - `+` is synchronized with system clipboard
  - `*` is synchronized with selection clipboard (only on \*nix systems)
9. The black hole register (`_`) - Everything written here will disappear forever.
10. The last search pattern register (`/`) - contains last search

#### Appending a recording

1. Hit `qa` to record keystrokes to register `a`, stop recording by hitting `q`.
2. Realize you forgot some keystrokes
3. Execute keystrokes to be sure you're at the last position of your recording.
4. Hit `qA` to append to register a. Hit `q` again to stop recording.

#### Using registers in insert/command line modes

| keystroke | action
| --- | ---
| `<C-r><reg>` | put content of register <reg> in current buffer

#### Expression register

| keystroke | action
| --- | ---
| `<C-r>=` | Use expression regiseter in insert/command line mode. This will move to command line mode, and from there, type anyt Vimscript expression such as `system("ls")` and `4+4`.

#### Clearing a register

| keystroke | action
| --- | ---
| `qaq` | start a recording and stop recording, which clears a register

## Substitute command

Search command: `:s/<pattern>/<replacement>/<flags>`, which replace pattern with replacment text, and flags modifies command behavior. Replacement text is not required.

The `/` separator can be any characters except:
- alphanumerical characters (`[a-z][A-Z][0-9]`)
- double quote `"`
- pipe "|"

| keystroke | action
| --- | ---
| `:s` | repeat last substitute command without flags
| `:s/pattern/replacement/` | substitute first occurence of `pattern` on current line with `replacement`
| `:s#pattern#replacement#` | equivalent substitution to the command above, useful if there are URL in pattern or replacement
| `:s/pattern/` | delete first occurence of `pattern` on the current line
| `:s/pattern/replacement/g` | substitute every occurence of `pattern` on the current line
| `:%s/pattern/replacement/` | substitute every first occurence of `pattern` on each line
| `:$s/pattern/replacement/g` | substitute every occurence of `pattern` on each line
| `:1,10s/pattern/replacement/` | substitute every first occurence of `pattern` on first 10 lines
| `:s/pattern/replacement/ 10` | substitute every first occurence of `pattern` for current and next 10 lines
| `:1,10s/pattern/replacement/ 5` | substitute every first occurence of `pattern` for 10 lines and 5 lines below last line of range
| `:s g 10` | repeat last substitution without its flag, and add a new flag `g`, substitution happens 10 lines after last line of last substitution

#### Magical patterns

| keystroke | action
| --- | ---
| `\v` | very magic, have access to all regex metacharacters
| `\V` | very nomagic, have access to no regex metacharacter
| `:sm` | substitute magic, have access to all regex metacharacters except `(`, `)` and `|`
| `:sno` | substitute nomagic, have access to no regex metacharacter except `$`

For example, following commands are equivalent:
- `:%s/\V(/`
- `:%sm/(/`
- `:%s/\(/`

Metacharacter `~` represents the latest substituted string

#### Additional commands

| keystroke | action
| --- | ---
| `:&&` | repeat last substitute with its flags
| `:~` | repeat last substitute command with same replacement, but with last used search pattern.
| `&` | in normal mode, repeat last substitute without range and flags
| `g&` | in normal mode, repeat last substitute with range and flags and replace pattern with last used search pattern.

#### Substitute flags

| keystroke | action
| --- | ---
| `&` | use flags from previous substitute commands
| `c` | ask to confirm each substitution
| `g` | replace all occurences in each line
| `i` | pattern is case-insensitive
| `I` | pattern is case-sensitive
| `n` | only report number of match without substitute

## Global command

| keystroke | action
| --- | ---
| `:g/pattern/command` | runs command on patterns
| :g/useless/d | delete all lines containing pattern `useless`

#### Normal mode commands

| keystroke | action
| --- | ---
| `:norm` | apply normal mode keystroke in command mode
| `:norm!` | apply normal mode keystroke in command mode using default vim mapping.
| `:norm daw` | delete word under cursor
| `:g/useless/norm gu$` | lowercase every line containing pattern `useless`

## Marks

Marks `a-z` are local to one buffer, and marks `A-Z` are global to multiple buffers.

If you have a `viminfo` file set via option `viminfo` in vim, or if `shada` file set via option `shada` in neovim, marks are persisted.

Marks `0-9` are available when using a `viminfo` file in vim and `shada` file in neovim. They store position of your cursor each time you quit a file.
Mark `0` stores the last position, and mark `1` stores position before the last one, and so on.

| keystroke | action
| --- | ---
| `'<mark>` | move to first non-blank character of the line where mark was set
| `` `<mark> `` | move to exact position where mark was set
| `g'<mark>` | same as `'<mark>` without changing the jump list
| g\`\<mark\> | same as `` `<mark> `` without changing the jump list
| `:marks` | display mark set
| `:marks <mark>` | display some specific marks
| `:delmarks <mark> ` | delete mark
| `:delmarks!` or `:delm!` | delete all marks in range `a-z`
| `:marks <>` | display marks `<` and `>`
| `` `a,`bs/pattern/replacement/ `` | substitute first match of pattert with replacement from exact position of mark a to exact position of mark b

#### Special marks

| keystroke | action
| --- | ---
| `m<` or `m>` | set marks `'<` or `'>`, can be handy for keystroke `gv`
| `` `[ `` | move to the first character of previously changed/deleted/yanked content
| `` `[ `` | move to the last character of previously changed/deleted/yanked content
| ``` `` ``` | move to position before the latest jump from jump list (or where you've set with `m'` or `` m` ``)
| `'"` | move to position where you've closed current file for the last time
| `` `^ `` | move to position where you've used insert mode for the last time (this mark is used by keystroke gi under the hood)

## Manipulating numbers

| keystroke | action
| --- | ---
| `<C-a>` | increase the first digit or number on the line
| `<C-x>` | decrease the first digit or number on the line
| `g<C-a>` | first number of each line will be incremented sequentially if multiple lines are selected (useful for numbered list), otherwise same as `<C-a>`
| `g<C-x>` | first number of each line will be decremented sequentially if multiple lines are selected (useful for numbered list), otherwise same as `<C-x>`

A prefix count can be prepended to above keystrokes, such as `12<C-a>`.

These keystrokes can work on unsigned binary, octal, hexadecimal numbers, and alphabetical characters. Behaviors depend on value of option `nrformats`. The option should not have `alpha` as part values, or keystrokes will increment/decrement the first alphabetical character of the line.

## Sorting text

| keystroke | action
| --- | ---
| `:sort` or `:sor` | sort lines depending on range, if no range given, all lines are sorted
| `:sort!` or `:sor!` | reverse order of `:sort`

Options:

| keystroke | action
| --- | ---
| `i` | ignore case
| `n` | sort depending on the first decimal on the line
| `f` | sort depending on the first float on the line
| `/pattern/` | sort depending on what comes after the match
| `r` | combined with `/pattern/`, sort depending on matching pattern

For example, if you want to sort lines in a csv file (delimited by `,`) depending on second columns: `:sort /[^,]*,/`

# resources

[A Great Vim Cheat Sheet](http://vimsheet.com)

[Advanced Vim Cheat Sheet](http://vimsheet.com/advanced.html)

[Vim Text Objects: The Definitive Guide](https://blog.carbonfive.com/2011/10/17/vim-text-objects-the-definitive-guide/)

[Vim Tips Wiki: Using marks](https://vim.fandom.com/wiki/Using_marks)

[Vim registers: The basics and beyond](https://www.brianstorti.com/vim-registers/)

[Is Vim Really Not For You? A Beginner Guide](https://thevaluable.dev/vim-beginner/)

[Graphical vi-vim Cheat Sheet and Tutorial](http://www.viemu.com/a_vi_vim_graphical_cheat_sheet_tutorial.html)
