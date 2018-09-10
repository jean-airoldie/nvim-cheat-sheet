# nvim-cheat-sheet
A list of helpfull commands in nvim

## Before reading
* Always assume we are in normal mode unless explicitely specified
* This guide uses the default commands (no remapping unless explicity specified)
* For a config template: see my [nvim config here](https://github.com/jean-airoldie/dotfiles)

## The basics

### Open File
`:help file`
* `nvim filename1 filename2` open files `filename1` and `filename2` with nvim

### Normal Mode
`:help normal`
* `ESC` or `ctrl+[` return to normal mode

### Save File
`:help save-file`
`:help quit` \
*Note that `!` can be appended to the following commands to force it (i.e `:wq!`)*
* `:w` write to current file
* `:q` quit file (must be saved before)
* `:wq` or `:x` write & quit
* `:saveas` save current file into another file \
*Here are a few equivalent shorthands*
* `ZZ` is like `:x`
* `ZQ` is like `:q!`

## Insert Mode
`:help insert`
* `i` enter insert mode

## Replace mode
`:help replace`
* `r` enter replace mode

### Movement
`:help movement`
* `gg` go to first line of file
* `G` go to last line of file
* `5G` go to line 5
* `%` go to next part of parenthesis, bracket etc.
* `up` or `k` move up
* `down` or `j` move down
* `left` or `h` move left
* `right` of `l` move right

### Undo / Redo
`:help undo`
* `u` undo one change
* `CTRL-R` redo one change
* `:undolist` show the undo list (usefull when undo branching happens)

### Paste
`:help paste`
* `p` paste content of unnnamed register after cursor
* `"aP` paste the content of register `a` before cursor

### Yanking
`:help yank`
* `yw` yank word forward into unnnamed register
* `"ayW` yank WORD forward into register `a`
* `"+yy` yank current line to clipboard
* `y}` yank paragraph into unnnamed register

### Repetition
* `.` will repeat the previous command if possible \
(Concept) Many commands can be executed multiple times by prepending them with
any number, which represent the number of repetition we need.
* `5i` will enter insert mode and insert 5 times the content written
* `7dd` wil delete the 7 following lines, including the current one
* `99yy` will yank 99 lines, including the current one
* etc.

## The Advanced Stuff

### Searching
`:help search`
* `/word` to enter forward search mode and search `word`
* `n` while forward searching to go forward
* `N` while forward searching to go backward
* `*` search current word forward
* `#` search current word backwards
* `ctrl+o` return to previous position before search

### Registers (yank & paste buffers)
`:help registers`
* `""` the unnamed (default) register
* `"a` overwrite version of register `a`
* `"A` append version of register `a`
* `"+` the clipboard
* `"_` the black hole register, does nothing (not affecting the other registers
* `"/` the last used regex register

## Insert Completion
`:help ins-completion` \
*while in insert mode*
* `ctrl+n` any completion
* `ctrl+x + ctrl+n` keyword in file
* `ctrl+x + ctrl+k` words in dictionary
* `ctrl+x + ctrl+t` words in thesaurus
* `ctrl+x + ctrl+f` filenames

### Recording
* `qa` will start a recording in overwrite mode in register `a`
* `qA` will start a recording in append mode in register `a`
* `@a` will execute the recording in regester `a`

### Formatting
`:help formatting`
* `~` swap character between UPPER lower
* `gUw` make word UPPER
* `guw` make word lower
* `gqq` format current line
* `gqap` format current paragraph
* `gqG` format from current line to end of file

### Tags
`:help tags`
* [ctags](https://github.com/universal-ctags/ctags) must be present in the root directory to allow jumping.
* `ctrl+]` jump to tag on cursor
* `ctrl+t` go to position prior to tag jump

### Jump Motions
`:help jump-motions`
* `ctrl+o` go to previous position in jump list
* `ctrl+i` go to next position in jump list
* `:ju` show jump list

### Substitute (search and replace)
`:help substitute`
* `:range/regex_expr/replacement/flag`

#### Range
`:help range`
* `%` for the whole file.
* `'<,'>` for the lines of visually selected block. This might get you more than you want of the visual selection starts or ends in the middle of a line. The whole line is included.
* `'a,'b` from mark a to mark b.
* `.,$` from the current line to the end of the file.
* `.,.+10` from current line to 10 lines below current line
* `:help :range` for more

#### Regex
`:help regex`

#### Flag
`:help s_flags`
* `c` ask to confirm before each substitution
* `g` replace all occurences on the line (as opposed to the first occurence)
* `i` ignorecase for regex pattern
* `I` dont ignorecase for regex pattern

#### Folding
`:help folding`
* `za` while in a code block to toggle between collapsed / normal

### Visual Block mode
`:help block`
* `ctrl+v` enter visual block mode (I remapped to v cuz normal visual mode sucks) \
*while in visual block mode*
* `I` enter block insert mode which will insert before the cursor for every line in block
* `shift+$` select the whole block from left to right
* `A` enter block append mode which will append after the cursor for every line in block
