To searhc for multiple file patterns use the `-o` option, but make sure to pair
it with the same search directive
```bash
$ find . -type f -iname '*.pdf' -o -iname '*.txt'
```
Something like that.  There is some way to do this with `(...)` magic but I
don't know what it is yet.
