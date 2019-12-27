# vim cheatsheets

## modes

| mode        | purpose
| ---         | ---
| normal mode | navigate the structure of the file
| insert mode | edit the file
| visual mode | highlight portions of the file to manipulate at once
| ex mode     | command mode

## movements

#### Note: commands with [count] can be repeated by prepending a number of count

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

## edit text

## text objects

## highlight text

## copy/cut/paste

## exit

## search/replace

## tabs/windows

## registers

## marks

## Credit

https://github.com/nicknisi/vim-workshop/blob/master/vim-workshop.pdf

http://vimsheet.com

http://vimsheet.com/advanced.html
