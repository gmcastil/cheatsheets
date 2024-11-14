## Debugging Vim Configuration
### Logging Vim Startup
Since Vim lacks the ability to log every time a specific setting is changed, use
high verbosity, then log and grep the result:
```bash
$ vim -V9vimlog.txt
```
Another tactic is to set up an `autocmd` to log when a particular option
changes, such as `formatoptions`
```vimscript
:autocmd OptionSet formatoptions echom "formatoptions changed to: " . &formatoptions
```
It can be useful to log the messages window as well, 
```vimscript
TBD
```
Also potentially useful, is the `:scriptnames` output, which logs all sourced script
names and the order they were encountered.
## Common Vim Editing Tasks
### Convert Leading Spaces to Tabs
When copying and pasting C code, a lot of times the tabs will be converted to
spaces in the Vim buffer. To replace the leading spaces with the appropriate
number of tabs, use something like the following:
```vimscript
:set tabstop=2      " Set this to match the text to be fixd
:set noexpandtab    " Use tabs, not spaces
:%retab!            " Retabulate the whole file
```
This is essentially telling the editor to interpret two spaces as a tab, to use
tabs instead of spaces, and then retabulate the whole file (or a visually
selected area of text).  It's quite useful to use `:set list` prior to doing
this so that the whitespace is actually visible.

[Reddit Vim on FileType specific items](https://www.reddit.com/r/vim/wiki/where_to_put_filetype_specific_stuff/#wiki_in_a_proper_filetype_plugin)

