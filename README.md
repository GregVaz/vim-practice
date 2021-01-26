# Vim Editor

## Introduction
It’s a editor, one of the most popular text editors.
It’s a clone of the VI editor, and is, written by, Bran Moolenaar.

* Features
  * It's memory footprint is very low
  * It's comman center. Perform coplet text related task with few commands
  * It's highly configurable
  * Programming

## Vim modes
**Command mode**

You can enter editor commands in this mode like copy, paste, delete, replace and many more.

**Insert mode**

You can use this mode to enter/edit text.
`Press i` to enter this mode

**Visual mode**

You can visually selec text and run commands on selected sections.
* To switch from command mode to visual mode **type v**
* To switch from any other mode to visual mode first back to command mode by **pressing Escape _ESC_**

## Basic Commands
### Command mode
`:w` -> Save the file

`:q` -> Quit vim

`:q!` -> Quit editor without saving changes

`:wq` -> Save the file and then quit vim

> We can combine (with theirs own rules) the different commands of vim

### Basic movement around vim

`h` -> move to the left

`l` -> move to the right

`j` -> move to the bottom

`k` -> move to the top


### Basic movement on screen

`H` -> move to the top

`M` -> move to the middle

`L` -> move to the bottom


#### Basic word movement

`w` -> move to the start of the next word

`W` -> move to the start of the next word (words can contain punctuation)

`e` -> move to the end of the word

`E` -> move to the end of the word (words can contain punctuation)

`b` -> move to the beginning of the word

`B` -> move to the beginning of the word (words can contain punctuation)


Also you can use a n number of movement for this commands.

`3w` is the same as pressing w three times

`9l` is the same as pressing l nine times


#### Go to matching parentheses %

`Press %` you can jump to the matching parenthesis or brackets (),[],{}


#### Go to start/end of line

`Press $` to go to the end of the line

`Press 0` to go to the beginning of the line

`Press g_` to jump to the last non-black character of the line

`Press fx` to jump to the next ocurrence of character x

`Press tx` to jump to the before next ocurrence of the character t

`Press zz` center cursor on the screen

`Press <C-e>` to move screen down one line (without moving cursor)

`Press <C-y>` to move screen up one line (without the cursor)

`Press <C-b>` to move back one fll screen

`Press <C-f>` to move forward one full screen

`Press <C-d>` to move forward 1/2 screen

`Press <C-u>` to move back 1/2 screen


#### Goto line 

`Press gg` takes you to the beginnig of the document

`Press G` takes you to the end of the document

`Press #G` to jump directly to a specific line


#### Search /text with n and N

`Press /` and then write the text you are looking for

`Press n` if you do a search then you can get the next occurrence

`Press N` if you do a search then you can get the previos ocurrence 



## Operator + Action = Action
|Trigger|Effect|
|-------|----------------|
|`c`|Change|
|`d`|Delete| 
|`y`|Yank into register| 
|`g~`|Swap case| 
|`gu`|Make lowercase| 
|`gU`|Make uppercase| 
|`>`|Shift right| 
|`<`|Shift left| 
|`=`|Autoindent| 
|`!`|Filter {motion} lines thought an external program| 


#### Insert a new line

`Press o` to create a new line below and start insert mode

`Press O` to create a new line above and start insert mode

`Press a` insert mode (append) after the cursor

`Press A` to go to the end of the line and enter on InsertMode

`Press i` to insert before the cursor

`Press I` to go to the beginning of the line and enter on InserMode

`Press ea` to insert (append) at the end of the word

`\<ESC\>` exit to insert mode


#### Removing a character

`Press x` to remove the character under the cursor

`Press X` to remove the character before under the cursor

`Press r` to replace the character under the cursor with a new character


#### Deleting the world

`Press dd` to delete a complete line

`Press dw` to delete the first word on the **right side**. This action copies the content and you can paste it

`Press d#w or d#e` to delete the number selected of words


#### Copy the world

`Press yy` to copy a line

`Press yw` to copy the first word on the **right side**. 

`Press p` to paste content of the buffer before the cursor position

`Press P` to paste content of the buffer after the cursor position


#### Repetition of previuos command

`Press .` to repeat the previous command

  
#### If you made a select without a where, don't worry you can undo

`Press u` for undo changes

`Press <C-r>` for redo changes


#### Replacing the mistakes

`:%s/true/false/g` -> This command works as a regular expression for search and replace.

This command will replace all the *true* with *false*. The **g** at the end is responsible for extending the search and replacing for all the matches. Otherwise, only the first match is replaced.

`:s/true/false/g` -> Here the ':s' command will do the exact same function as above but only **in the current line instead of the entire file**

There are different flags as *g* that we can use in way to modify the result.
Ex. `:%s/true/false/gci`

`i flag` -> That make it case insensitive to characters in search, because the default is case sensitive.

`c flag` -> This can helps a lot, It's the *confirmation* flag, Vim wil ask you to confirm if you want to perform a replace on each other



#### Insert text repeatedly

Pressing the number then the word i and finally the word or letter

`[0-9]i{a-zA-Z}* <ESC>`
`5iHello ESC` -> HelloHelloHelloHelloHello



### Use counts to Do Simple Arithmetic

The \<C-a\> and \<C-x\> commands perform addition and substration on numbers.

| Keystrokes | Buffer contents |
| :----------------: | -------------------------------------- |
| {start} | .blog { background-position: 0px 0px } |
| `yyp` | .blog { background-position: 0px 0px } |
| `cW.news<ESC>` | .news { background-position: 0px 0px } |
| `180<C-a>` | .news { background-position: 180px 0px } |
| `180<C-x>` | .news { background-position: 180px -180px } |


### Insert mode

#### Make corrections instantly from Insert Mode

`<C-h>` -	Delete back one character (backspace)

`<C-w>` -	Delete back one word

`<C-u>` -	Delete back to start of line


#### Get back to the Normal Mode

`<Esc>` -	Switch to Normal Mode

`<C-[>` -	Switch to Normal Mode

`<C-o>` -	Swtich to Insert Normal Mode

> Insert Normal Mode is a speacial version of Normal Mode, which gives us one bullet. We can fire off a single command, after which we'll be returned to 


#### Paste from a Register without Leaving Insert Mode

`<C-r>0` -	Paste the text that we just yanked at the current cursor position


#### Do calculations in place

`<C-r>=<Operation><CR>` -	You can get airthmetic operations on insert mode, press <C-r> with = and this open a prompt at the bottom of the screen where we can type the expression that we want to evaluate.
Ex. 6 tacos, each costing $15, totals $ -> <C-r>=6\*15<ENTER> -> totals $90


#### Insert unusual characters by Character Code

`<C-v>{code}` -   Insert any arbitrary character if we know its numeric decial code. Vim expects the numeric code to consist of three digits.

`<C-v>u{code}` -   Insert any arbitrary character if we know its numeric hexadecimal code. Vim expects the numeric code to consist of four digits.

`ga` -	to find out the numeric code for any character in your document


#### Overwrite existing text with Replace Mode
> Replace mode is identical to Insert mode, except that it overwrites existing text in the document.

`R` -	Press R from Normal Mode to acces to Replace mode, here you typing as in Insert Mode but in Replace mode the line length doesn't change.


### Visual Mode
> Visual mode allows us to define a selection of text adnd then operate upon it.

`v` -	Enable character-wise Visual mode

`V` -	Enable line-wise Visual mode

`<C-v>` -	Enable block wise Visual mode

`gv` -	Reselect the last visual selection

`<C-[> | <ESC>` -	Switch to Normal mode


#### Change columns of text

`<C-v>jje` -	enable line-wise visual mode, then we down two lines and go to the end of the word.

`c` -	Change to insert mode (change), and write the new word fo replacement

`<Esc>` -	And finally you will see the changes on all the selections


