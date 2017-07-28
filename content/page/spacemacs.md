---
title: Spacemacs
---

## Installation

[Windows](https://www.youtube.com/watch?v=uaoN1rLfP00)
[Linux](https://www.youtube.com/watch?v=xFp9Jahs8Ng)

## Configuration

Set your dotfile to `~/spacemacs.d/`-folder. You can syncronize your dotfiles between computers and have your own setup up and running just syncing this folder.




## Vim Bindings

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

`:%s/^/!/g` to insert ! character on beginning of all lines. Dropping last g will do it to first match. gs would prompt every change

#### Doing same thing for visual selection

`:'<,'>normal I!ENTER`


### Indenting

`gg=G` autoindents whole file

### operators

* y yank
    * `yy` yank line
* c change
    * `c` change end of line
    * `cw` change rest of word
    * `ci[w/./)]` change in word/./)
* `p` paste after cursor
* `p` paste before cursor
* `

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



### Exercises

#### Remove quotes around text

"Remove quotes around this text" is `di"P2x`

#### Remove parentheses 

10
100
(Remove parentheses around this text) is `di)h2x`

#### Yank 2 first sentences

Yank first sentence. And second. But not the third. is `y2f.`

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


#### Code folding

`zm` fold
`zr` open folded

## Moving between buffers

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

## Very magic and no magic

## Substituting

s first line %s all lines

#### Flags

`c` confirmation
`g` global, apply to all cases in a row
`n` tally
`e` supres error messages
`&` apply previously used flags
 fs

## Sorting

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

