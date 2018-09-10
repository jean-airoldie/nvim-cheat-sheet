# nvim-guide
Various helpfull nvim commands.

*Note that we assume we are in normal mode unless explicitely specified*
## Movement
`:help movement`
* `gg` go to first line of file
* `G` go to last line of file
* `5G` go to line 5
* `%` go to next part of parenthesis, bracket etc.

## Formatting
`:help formatting`
* `~` swap character between UPPER lower
* `gUw` make word UPPER
* `guw` make word lower
* `gqq` format current line
* `gqap` format current paragraph
* `gqG` format from current line to end of file

## Tags
`:help tags`
* [ctags](https://github.com/universal-ctags/ctags) must be present in the root directory to allow jumping.
* `ctrl+]` jump to tag on cursor
* `ctrl+t` go to position prior to tag jump

## Jump Motions
`:help jump-motions`
* `ctrl+o` go to previous position in jump list
* `ctrl+i` go to next position in jump list
* `:ju` show jump list

## Undo / Redo
`:help undo`
* `u` undo one change
* `CTRL-R` redo one change
* `:undolist` show the undo list (usefull when undo branching happens)

## Searching
`:help search`
* `/word` to enter forward search mode and search `word`
* `n` while forward searching to go forward
* `N` while forward searching to go backward
* `*` search current word forward
* `#` search current word backwards
* `ctrl+o` return to previous position before search

## Substitute (search and replace)
`:help substitute`
* `:range/regex_expr/replacement/flag`

### Range
`:help range`
* `%` for the whole file.
* `'<,'>` for the lines of visually selected block. This might get you more than you want of the visual selection starts or ends in the middle of a line. The whole line is included.
* `'a,'b` from mark a to mark b.
* `.,$` from the current line to the end of the file.
* `.,.+10` from current line to 10 lines below current line
* `:help :range` for more

### Regex
`:help regex`

### Flag
`:help s_flags`
* `c` ask to confirm before each substitution
* `g` replace all occurences on the line (as opposed to the first occurence)
* `i` ignorecase for regex pattern
* `I` dont ignorecase for regex pattern

## Yanking
`:help yank`

## Registers (yank buffers)
`:help registers`
* `""` the unnamed (default) register
* `"a` overwrite version of register `a`
* `"A` append version of register `a`
* `"+` the clipboard
* `"_` the black hole register, does nothing (not affecting the other registers
* `"/` the last used regex register

## Insert Completion
`:help ins-completion`
*while in insert mode*
* `ctrl+n` any completion
* `ctrl+x + ctrl+n` keyword in file
* `ctrl+x + ctrl+k` words in dictionary
* `ctrl+x + ctrl+t` words in thesaurus
* `ctrl+x + ctrl+f` filenames

## Visual Block mode
`:help block`
* `ctrl+v` enter visual block mode (I remapped to v cuz normal visual mode sucks)
*while in visual block mode*
* `I` enter block insert mode which will insert before the cursor for every line in block
* `shift+$` select the whole block from left to right
* `A` enter block append mode which will append after the cursor for every line in block
