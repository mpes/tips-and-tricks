# VIM
### Commandline
* `vim filename` Opens new file in Vim
* `vim -p` option opens each specified file in a separate tab (up to the value of the 'tabpagemax')
* `vim -N` opens Vim in new mode incompatible with Vi (If a .vimrc file exists, vim will start in nocompatible mode automatically) You can also get nocompatible mode with these `:set nocompatible`
* `find . | vim -` streams output into vim

### Keyboard shortcuts

* <kbd>ctrl + L</kbd> refreshes screen
* <kbd>ctrl + ^</kbd> switches to next file when multiple opened
* 
### General 
 `:w !sudo tee %` saves the file with sudo
 <kbd>ctrl + r =</kbd> you can type expressions *2+2* or system commands *system('pwd')* and results will be placed at cursor when in insert mode
 
## Settings
### marks
* `ma` creates mark named *a*
* `` `a`` jumps to mark *a* position
* `'a` jumps to the begginning of the line of mark *a*
### options tricks

* `:set list` or `:set nolist` - turn on/off
* `:set list?` show current value
* `:set list&` set to default value  
* `TAB` cycles through possible command completions
* <kbd>CTRL-d</kbd> - lists possible command completions

## Configuration rules

The best way is put them to file (`~/.vimrc`). Default path for configuration.

* `syntax on` - enable syntax highlighting
* `colorscheme molokai` - set editor theme
* `set number` - enable line number
* `set noic` - don't ignore letter case, ex. in searching
* `set expandtab` - change tabulators to spaces
* `set tabstop=4` - number of characters as indent with TAB key
* `set shiftwidth=4` - number of characters as indent with insertions
* `set mouse=a` - enable mouse in editor
* `set background=dark` - little change for brighter colors
* `set autoindent` - enable automatic indention
* `set hlsearch` - enable highlighting after searching process
* `set incsearch` - run searching process after you press any char (after '/')
* `set nowrapscan` - stop navigate throught search result when file is ends
* `set nowrap` - don't wrap lines
* `set clipboard=unnamedplus` - Vim use the same buffer as OS
* `set guifont=Inconsolata\ 12` - change font in editor
* `set ignorecase` case insensitive
* `set smartcase` use case if any caps used 
* `set incsearch` show match as search word is typed
* `set hlsearch` search highlighting
### Modelines
Modelines allow you to set variables specific to a file. By default, the first and last five lines are read by vim for variable settings. For example, if you put the following in the last line of a C program, you would get a textwidth of 60 chars when editing that file:
* `/* vim: tw=60 ts=2: */`
### Folding 
select block, then `:fold`
* `zo` - open
* `zc` - close
### Word & line completion
In insert mode, try:
* <kbd>ctrl-n</kbd>, <kbd>ctrl-p</kbd>  next/previous word completion (similar word in current file)
* <kbd>ctrl-x</kbd><kbd>ctrl-l</kbd> (<kbd>ctrl-n/p</kbd>)    - line completion
* `:set dictionary=/usr/share/dict/words`
* <kbd>ctrl-x</kbd><kbd>ctrl-k</kbd>     - dictionary completion
* <kbd>ctrl-w</kbd> erases word (insert mode...
* <kbd>ctrl-u</kbd> erases line  ...or on command line)

### set operation

* `:set list` show hidden characters
* `:set ruler` show the cursor position in the status bar
* `:set number` show line numbers
* `:set laststatus` always show the statusbar
* `:set syntax=enable` enable syntax highlighting
* `:set filetype=xml` sets syntax to XML
* `:set softtabstop=2` control how many columns vim uses when you hit Tab in insert mode
* `:set tabstop 8` - tabs are at proper location
* `:set expandtab` - don't use actual tab character (ctrl-v)
* `:set shiftwidth=4` - indenting is 4 spaces
* `:set autoindent` - turns it on
* `:set smartindent` - does the right thing (mostly) in programs
* `:set cindent` - stricter rules for C programs
* `:e .` browse directory
 `i` long, wide or tree
 `s` sort on name, siize or date
 `r` reverse order
 `gh` hide/show dotfiles
 `x` opens with associated application
 `d` makes directory
 `D` deletes file or dir
 `R` renames
 `-` goes up one level
* `:e filename` opens a file
* `:cd path` changes working directory. Then we can use relative paths and use TAB to autocomplete
* `:tab ball` moves opened files to tabs
* `:set nocompatible` swithc to nocompatible mode
### Editor

#### Editor: Open files

* `:e FILENAME` - open file to edit, replaced current window with file
* `:tabe` (`:tabedit`) - open file in new tab
* `:tabc` (`:tabclose`) - close current tab
* `gt` / `gT` go to next/previous tab

#### Editor: Searching, greping etc

* `:noh` (`:nohl`, `:nohlsearch`) - clear highlight after search
* `/foo` - searching text `foo` in whole document (forwards)
* `?foo` - searching text `foo` in whole document (backwards)
* `:cw` - show result list after searching
* `:%s/foo/bar/g` - replace globally `foo` to `bar`
* `*` - searching word where cursor is on it (forwards)
* `#` - searching word where cursor is on it (backwards)
* `g*` - searching partial words where cursor is on it (forwards)
* `g#` - searching partial words where cursor is on it (backwards)
* `/\<foo` - searching words starting with `foo`
* `/foo\>` - searching words ending with `foo`
* `/\<foo\>` - searching words `foo`

* <kbd>TAB</kbd> - cycles through possible command completions
* <kbd>CTRL-d</kbd> - lists possible command completions
                  (repeat with n)
* <kbd>ctrl-o</kbd>, <kbd>ctrl-i</kbd> go through jump locations
* `[I` show lines with matching word under cursor

#### Editor: Misc

* `so ~/.vimrc` - reload configuration in opened editor
* `:retab` - replace current whitespaces with sets in `.vimrc` file
* `:!ls` - run command `ls` in shell
* `:!sort` sort (selected)
* <kbd>Ctrl + a</kbd> - increment number by one you are at
* <kbd>Ctrl + x</kbd> - decrement number by one you are at
* <kbd>ZZ</kbd> - write files and quit
* <kbd>ZQ</kbd> - quit all instances of vim
* <kbd>Ctrl + z</kbd> - hide Vim to background - use `fg` in terminal to bring it to foreground
* <kbd>Ctrl + l</kbd> - redraw Vim windows 
* <kbd>ctrl-t</kbd>,<kbd>ctrl-d</kbd>- indent current line forward, backwards (insert mode)

#### reformatting
* `V=` select text, then reformat with =
* `=`  will correct alignment of code
* `==` one line; 
* `gq` reformat paragraph
Options to change how automatic formatting is done:
`:set formatoptions` (default "tcq")
* `t` - textwidth
* `c` - comments (plus leader -- see :help comments)
* `q` - allogw 'gq' to work
* `n` - numbered lists
* `2` - keep second line indent
* `1` - single letter words on next line
* `r` - (in mail) comment leader after 
Other related options:
* `:set wrapmargin`
* `:set textwidth`

### Cursor navigation

* <kbd>Ctrl + e</kbd> - scroll the window down
* <kbd>Ctrl + y</kbd> - scroll the window up
* <kbd>Ctrl + f</kbd> - scroll down one page
* <kbd>Ctrl + b</kbd> - scroll up one page
* `H` - move cursor to the top of the viewport
* `M` - move cursor to the middle of the viewport
* `L` - move cursor to the bottom of the viewport
* `gg` - move cursor to the top of file
* `G` - move cursror to the bottom of file
* `{` - move cursor to previous empty line
* `}` - move cursor to next empty line
* `%` - jump between bracket in line
* `30%` - move cursor to line which is 30% of the top of file
* `zz` - center verticaly line with cursor
* ` `` ` - back cursors to previous place
* <kbd>Ctrl + ^</kbd> - return to previous file

### search and replace
|Range|Description|Example|
|-------|-----------|---------|
|21|line 21|21s/old/new/g|
|1|first line|1s/old/new/g|
|$|last line|$s/old/new/g|
|.|current line|.w single.txt|
|%|all lines (same as 1,$)|%s/old/new/g|
|21,25|lines 21 to 25 inclusive|21,25s/old/new/g|
|21,$|lines 21 to end|21,$s/old/new/g|
|.,$|current line to end|.,$s/old/new/g|
|.+1,$|line after current line to end|.+1,$s/old/new/g|
|.,.+5|six lines (current to current+5 inclusive)|.,.+5s/old/new/g|
|.,.5|same (.5 is interpreted as .+5)|.,.5s/old/new/g|

### delete
* `:1,.d` deletes from first line to current(included)
* `:.+1,$-1d` deletes from first line to current (included)

## Visual mode
* `o` in selection toggles cursor between first and last cursor positions
* <kbd>ctrl-v</kbd>  - selects columns
* `gv`      - reselect block

## Insert mode
* `ctrl+d` shift text left in insert mode
* `ctrl+t` shift text right in insert mode

#### Editor: Markers
Marker names sets the area where we can use them: `a-z` within current file, `A-Z` across files
* `m{char}` - save current position into `{char}`
* \`{char} - go to saved mark
* `d'{char}`  - delete from current position to mark k
* `:marks` - display list of current saved markers

### Tips
* `:123put =range(11,15)`  inserts number 11-15 after line number 123
* `:for i in range(1,10) | put ='192.168.0.'.i | endfor` generates ip addresses 192.168.0.1 to 192.168.0.10
* `gf` goes to the file under the cursor
