---
title: Spacemacs
---

## Installation

[Windows](https://www.youtube.com/watch?v=uaoN1rLfP00)
[Linux](https://www.youtube.com/watch?v=xFp9Jahs8Ng)

## Configuration

Set your dotfile to `~/spacemacs.d/`-folder. You can syncronize your dotfiles between computers and have your own setup up and running just syncing this folder.


## Vim Bindings

### Search


### Movements

`gg` first line
`G` last line
`Ctrl b` `Ctrl u` `Ctrl d` `Ctrl f` 
`k`
`j`
`h`
`l`
`f`
`F`
`t`
`T`
`0`
`w`
`W`
`e`
`E`
`O`
`o`


### enter insert mode

`i` before cursor
`I` begin of line
`a` append cursor
`A` end of line
`O` previous line
`o` next line
`s` sustitute character
`s` substitute line (same as `cc`)
`c` substitute end of line

### visual mode

* `v` select from cursor
* `V` select line
* `^v` ???

### Visual block mode

`Ctrl-v` to enter mode. Select lines. `A` to start editing and `ESC` to finish.

### EX commands

#### Replacing through document

`:%s/^/!/g` to insert ! character on beginning of all lines. Dropping % would apply this to one line. Dropping last g will do it to first match. gs would prompt every change

#### Doing same thing for visual selection

`:'<,'>normal I!ENTER` 


### Indenting

`gg=G` autoindents whole file
`>>` indent right
`<<` indent left

### operators

* y yank
    * `yy` yank line
* c change
    * `c` change end of line
    * `cw` change rest of word
    * `ciw` change in word
    * `caw` change also outside the word
    *  
* `p` paste after cursor
* `P` paste before cursor

### Objects

w word
p paragraph
a argument
s sentence
) parentheses
} braces
] brackets
' single quotes
" double quotes
` backticks
t tag

### Go places

`gf` go to file in same directory
``.` go to last change`
``^` go to last insertion

### Strings in storage

`"%` path of current file
`"#` path of current init.el file
`".` last inserted text
`":` last ex command
`"/` last searh

### Macros

`qa` start recording a macro to a register and `q` to stop it
`@@` play previous macro, after this use `.`
`qA` append macro in `A`

#### Example macro

If one would like start a row with "var" and end it with ";". Then you could `qaA;<Esc>Ivar<Space><Esc>q`

On a empty line result would be "var ;". A row with "a", would turn into "var a;".

If I would like to use this macro for multiple lines. I could call it from other macro eg. `qb@aj^q` or could just append movement to row below by `qAj^q` and then call @a/@b with proper count or I could visually selected rows then run `: normal @a`

a
b
c

wound turn into

var a;
var b;
var c;


### Args???

#### code folding

`zm` fold
`zr` open folded


### Very magic and no magic

### Substituting

s first line %s all lines

#### Flags

`c` confirmation
`g` global, apply to all cases in a row
`n` tally
`e` supres error messages
`&` apply previously used flags
 fs

### Sorting

`vip:sort`

ö
ä
l
c
b
a 

and you get

a 
b
c
l
ä
ö

to reverse it use 

* `sort!`
* `sort u` for removing duplicate rows
* `sort n` sort using numerical sort

### Exercises

#### Remove quotes around text

"Remove quotes around this text" is `di"P2x`

or shortly `ds"`

### Remove parentheses 

(Remove parentheses around this text) is `di)h2x`

or shortly `ds"`

#### Yank 2 first sentences

Yank first sentence. And second. But not the third. is `y2f.` or `y2)`

#### Make a increasing list

"101 This is an item." repeat sentence increasing the number.
On first row typ: qaYp[ctrl-a]q8@a

Result is:
101 This is an item.
102 This is an item.
103 This is an item.
104 This is an item.
105 This is an item.
106 This is an item.
107 This is an item.
108 This is an item.
109 This is an item.
110 This is an item.
111 This is an item.


{  }	beginning of previous, next paragraph
( )	beginning of previous, next sentence


#### code folding

`zm` fold
`zr` open folded

## Moving in/between files/buffers/files/projects

search: use `/<Enter>` and then `n` or `p`
SPC TAB previous buffer
SPC j w jumps to word
SPC ` moves backward 
SPC p p find a project
SPC p f find a file in this project

* SPC b
** . 
** b
** C-z actions
** B IBuffer
** d delete buffer
** P copy from clipboard to buffer
** Y copy to clipboard

* SPC f
** c copy buffer to a new file name
** C convert line endings
** s save buffer
** D delete file and buffer
** f find file
** j jump to directory of file
** S save all buffers
** e d go to .spacemacs
** e f .spacemacs faq
** e R apply changes in dotfiles
** e v show and copy spacemacs version
** e h HELP


## Org mode

When org installed you can find a ton under `SPC m`

* M arrows ... moves item up, down, demote, promote
* M RET ... inserts a new heading/list item
* S arrows ... switch between todo and priority states
* SPC m - ... changes list style
* SPC : ... tags
* SPC , ... ctrl c ctrl c
* C-c C-z C-a Archive a entry
* C-c C-z C-a Archive a subtree
* C-u C-c C-x C-s Serch all done under subtree and archive with prompt
* col view and archive property:https://www.youtube.com/watch?v=BeAtCVZpHCg&index=20&list=PLVtKhBrRV_ZkPnBtt_TD1Cs9PJlU0IIdE
* Tables
| Nimi            | titteli              | työpaikka |
|-----------------|----------------------|-----------|
| Risto Kaartinen | työelämäasiantuntija | Keva      |
| Joku muu        | johtaja              | Kela      |
|                 |                      |           |
* Source code

#+BEGIN_SRC R
mtcars

#+END_SRC


## Insert stuff


* SPC i
** e emoji
** j, J, k, K insert empty line or [ SPC or space ]
** l lorem ipsum text
** s Helm yasnippets

## Ess layer

* M {/} move up and down in repl
* C-c C-c break
* M n 1 1

## Magit layer

* . vcs microstate
* b git blame microstate
* c commit
* C checkout
* d diff
* D diff head
*
* S/U (un)stage whole file
* t time machine microstate

`SPC g s` magit status:
c commit
F pull
p push
ll log
r rebase
b branch


## Undo/redo

SPC a u undo tree
u undo
Ctrl ? redo

## File system

`SPC a r` to ranger
`SPC a d` to dired

## Inser a emoji

`SPC a E`

## Commenting

SPC ; comment operator (visual selection, a p paragraph, i i idented text)

* SPC c
** l comment line
** l comment line invert
** p comment paragraph
** P comment paragraph invert
** t comment to line
** T comment to line invert

## Color map

SPC C l

## Unsorted

SPC ! shell command
SPC ? a list of helm session keybindings
SPC F1 Fuzzy search of emacs stuff

## Calculator

`SPC a c` 

Easy way make calculations is with `q`.

To return with last result `y`

https://www.youtube.com/watch?v=D9lmCbLGZ_c


## Evil exchange

Exchanges location of two objects (words, lines....)

fi|rst second
`gxw.`
result: second first

`gxx` for lines

## Evil-args

For example, `cia` transforms:

`function(arg1, ar|g2, arg3)
function(arg1, |, arg3)`

`daa` transforms:

`function(ar|g1, arg2, arg3)
function(|arg2, arg3)`

## Symbol highlight transient state

Over a word press `*`

* `n` jumps next same word occurence in that file
* `p`/N jumps back ...
* `e` starts iedit (edit all occurences)
* `b` searches same in buffers
* `p` searches same in projects

## Pasting transient state

Press `p`` to enter this state.

* `ctrl-j` and `ctrl-k` scroll through kill ring
* `p` to paste under or `P` before cursor


* Dired mode : 1. Copy file : `C`
               2. Delete the file : `D`
               3. Rename the file : `R`
               4. Create a new directory : `+`
               5. Reload directory listing : `g`
