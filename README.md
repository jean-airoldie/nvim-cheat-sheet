# nvim-guide
Various helpfull nvim commands.

## Substitute (search and replace)
`:help substitute`

### Ranges
`:help range`
#### TL;DR
* `%` for the whole file.
* `'<,'>` for the lines of visually selected block. This might get you more than you want of the visual selection starts or ends in the middle of a line. The whole line is included.
* `'a,'b` from mark a to mark b.
* `.,$` from the current line to the end of the file.
* `.,.+10` from current line to 10 lines below current line
* `:help :range` for more
