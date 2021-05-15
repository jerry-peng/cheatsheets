### ALE

ALE (Asynchronous Lint Engine) provides linting and acts as a Vim language server protocol client.

ALEInfo
ALEDetail
ALELint
ALEFix
eLEFixSuggest
:help ale-integration-options

### argtextobj.vim

This plugin provides text-object `a` (function argument)

| command | action                  |
| ------- | ----------------------- |
| `aa`    | a function argument     |
| `ia`    | inner function argument |

### Fzf.vim

| Command           | List                                                                    |
| ----------------- | ----------------------------------------------------------------------- |
| `:Files [PATH]`   | Files (runs `$FZF_DEFAULT_COMMAND` if defined)                          |
| `:GFiles [OPTS]`  | Git files (`git ls-files`)                                              |
| `:GFiles?`        | Git files (`git status`)                                                |
| `:Buffers`        | Open buffers                                                            |
| `:Colors`         | Color schemes                                                           |
| `:Ag [PATTERN]`   | [ag][ag] search result (`ALT-A` to select all, `ALT-D` to deselect all) |
| `:Rg [PATTERN]`   | [rg][rg] search result (`ALT-A` to select all, `ALT-D` to deselect all) |
| `:Lines [QUERY]`  | Lines in loaded buffers                                                 |
| `:BLines [QUERY]` | Lines in the current buffer                                             |
| `:Tags [QUERY]`   | Tags in the project (`ctags -R`)                                        |
| `:BTags [QUERY]`  | Tags in the current buffer                                              |
| `:Marks`          | Marks                                                                   |
| `:Windows`        | Windows                                                                 |
| `:Locate PATTERN` | `locate` command output                                                 |
| `:History`        | `v:oldfiles` and open buffers                                           |
| `:History:`       | Command history                                                         |
| `:History/`       | Search history                                                          |
| `:Snippets`       | Snippets ([UltiSnips][us])                                              |
| `:Commits`        | Git commits (requires [fugitive.vim][f])                                |
| `:BCommits`       | Git commits for the current buffer                                      |
| `:Commands`       | Commands                                                                |
| `:Maps`           | Normal mode mappings                                                    |
| `:Helptags`       | Help tags <sup id="a1">[1](#helptags)</sup>                             |
| `:Filetypes`      | File types                                                              |

<c-j> or <c-k> or arrow keys to navigate result list

<c-t> open file in new tab

<c-v> open file in vertical split

<c-x> open file in horizontal split

<tab> <shift-tab> to mark multiple files

### Tagbar

This plugin provides an easy way to browse the tags of current file and get an overview of its structure.

| command                | action                                                               |
| ---------------------- | -------------------------------------------------------------------- |
| `:TagbarToggle`        | toggle tagbar window                                                 |
| `:TagbarOpen`          | open tagbar window                                                   |
| `:TagbarClose`         | close tagbar window                                                  |
| `:TagbarOpenAutoClose` | open tagbar window and jump to it, and auto close upon tag selection |
| `s`                    | switch sort mode (name/file order) in tagbar window                  |
| `q`                    | close tagbar window                                                  |
| `x`                    | toggle zooming tagbar window                                         |

### commentary.vim

This plugin adds shortcuts to comment codes.

| command                  | action                                                                       |
| ------------------------ | ---------------------------------------------------------------------------- |
| `gcc`                    | toggle comment a line                                                        |
| `gc`                     | toggle comment in visual mode                                                |
| `gc<motion>`             | toggle comment out target of a motion. Ex: `gcap` to comment out a paragraph |
| `:<num>,<num>Commentary` | toggle comment with line range                                               |
| `:g/TODO/Commentary`     | toggle comment all lines of code that matches `TODO`                         |

### vim-indent-object

| Key bindings | Description                                                 |
| ------------ | ----------------------------------------------------------- |
| `<count>ai`  | **A**n **I**ndentation level and line above                |
| `<count>ii`  | **I**nner **I**ndentation level (**no line above**)        |
| `<count>aI`  | **A**n **I**ndentation level and lines above/below         |
| `<count>iI`  | **I**nner **I**ndentation level (**no lines above/below**) |

### vim-easymotion

#### TODO

### vim-fugitive

:Git or :G for running envoking git within vim.

### vim-gitgutter

toggle with :GitGutterToggle
jump to next hunk (change): ]c
jump to previous hunk (change): [c.
Use the GitGutterFold command to fold all unchanged lines, leaving just the hunks visible. Use zr to unfold 3 lines of context above and below a hunk.

### vim-surround

change: cs<object><object>
delete: ds<object>
add: ys<text object><object>
add to line: yss<object>

object: `'`, `"`, (, ), [ ,], { ,}, t is tag,
close means no space

Press a capital V (for linewise visual mode) followed by S<p class="important">.

```
<p class="important">
  <em>Hello</em> world!
</p>
```

### vim-unimpaired

This package includes pairs of handy bracket mappings, which includes many bracket mappings.

There are some mappings that could be useful in the future.
- moving through
  - argumnet list
  - buffer list
  - location list
  - quickfix list
  - tag match list
- encoding/decoding XML/URL/C string

Line operations:

| Key bindings | Description                                                 |
| ------------ | ----------------------------------------------------------- |
| `[ `         | Add [count] blank line above                                |
| `] `         | Add [count] blank line below                                |
| `[e`         | Exchange current line with [count] lines above              |
| `]e`         | Exchange current line with [count] lines below              |

Paste operations:

| Key bindings | Description                                                 |
| ------------ | ----------------------------------------------------------- |
| `>p`         | paste after line, increasing indent                         |
| `>P`         | paste before line, increasing indent                        |
| `<p`         | paste after line, decreasing indent                         |
| `<P`         | paste before line, decreasing indent                        |
| `=p`         | paste after line, reindenting                               |
| `=P`         | paste before line, reindenting                              |

### vim-repeat

Add `.` repeat command support for key mappings. Some tpope plugins are supported. To add support to to a plugin is as simple as following command at the end of map function: `silent! call repeat#set("\<Plug>MyWonderfulMap", v:count)`
