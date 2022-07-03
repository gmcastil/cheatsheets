Basics
======

So the basic help and info commands all work as expected.  Run `help` for a list
of topics, followed by the class that you want information on.

General
=======

It is useful to define some terms.

A *stack frame* is a collection of all information on the stack pertaining to a
subprogram call.  A *call stack* may be composed of one or many stack frames.
Each stack frame corresponds toa  call to a function or procedure which has not
yet terminated with a return.

Breakpoints
-----------

Breakpoints get set with the `break` command and cleared with the `clear`
command.  

Useful Links
============
Some helpful resources on the web

The [GDB manual](https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_toc.html)

The [GDB man page](https://man7.org/linux/man-pages/man1/gdb.1.html) obviously
via ``man 1 gdb``. If you're brave, wander into the info pages.

This [MIT tutorial](https://web.mit.edu/gnu/doc/html/gdb_1.html) was helpful.

Two articles from [a RedHat
developer](https://developers.redhat.com/author/keith-seitz) on using GDB

[Part
2](https://developers.redhat.com/articles/2022/01/10/gdb-developers-gnu-debugger-tutorial-part-2-all-about-debuginfo)
[Part
1](https://developers.redhat.com/blog/2021/04/30/the-gdb-developers-gnu-debugger-tutorial-part-1-getting-started-with-the-debugger)


