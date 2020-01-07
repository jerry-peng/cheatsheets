## Vim Plugins Cheatsheet

### ALE

ALE (Asynchronous Lint Engine) provides linting and acts as a Vim language server protocol client.

#### TODO

### argtextobj.vim

This plugin provides text-object `a` (function argument)

| command | action
| ---     | ---
| `aa`    | a function argument
| `ia`    | inner function argument

### ctrlp.vim

Full path fuzzy *file*, *buffer*, *mru*, *tag*, ... finder for Vim.

#### TODO

### CamelCaseMotion

This plugin defines motions similar to `w`, `b`, `e`, `ge` that moves camel-wise in a camel-cased word.

### delimitmate

This plugin provides automatic closing of quotes, parenthesis, brackets, etc.

### Emmet-vim

This plugin provides support for expanding abbrevitions.

#### TODO

### indentLine

This plugin provides vertical lines at each indentation level.

### NERDtree

This plugin is a file system explorer for vim.

| command | action
| ---     | ---
| `?`     | quickhelp

### Tagbar

This plugin provides an easy way to browse the tags of current file and get an overview of its structure.

| command         | action
| ---             | ---
| `:TagbarToggle` | toggle the tagbar window

### vim-airline

This plugin draws status line for vim.

### vim-airline-themes

This plugin is the official theme repository for vim-airline.

### closetag.vim

This plugin closes HTML/XML tags.

### commentary.vim

This plugin adds shortcuts to comment codes.

| command                  | action
| ---                      | ---
| `gcc`                    | toggle comment a line
| `gc`                     | toggle comment in visual mode
| `gc<motion>`             | toggle comment out target of a motion. Ex: `gcap` to comment out a paragraph
| `:<num>,<num>Commentary` | toggle comment with line range
| `:g/TODO/Commentary`     | toggle comment all lines of code that matches `TODO`

### vim-easy-align

This plugin aligns texts.

### VimCompletesMe
