# parsecomb

A parser combinator library. There are not enough parsers implemented yet
to make this a useful library. The parsers that are implemented might be
buggy on top of it.

## Implemented parsers

A short list of parsers that are in fact implemented:

### either

Takes two parsers, either must work.

### seq

Takes two parsers and parses sequentially.

### string

Matches a given string.

### char

Matches a given char.

### many

Takes a parser that must match zero or more times. Think of the `*` operator in regexes.

### many1

Takes a parser that must match one or more times. Think of the `?` operator in regexes.

### skip

Takes a parser and skips its' input.

### parse-all

Takes a parser that must consume the entire input string.

## TODO

Lots. If you have any suggestions that are not in any parser combinator library
I know somewhat well (parsec, mpc), hit me up with your cool ideas.

## Known Bugs

This library does not handle left-recursive grammars well. This means that there
are some limitations on recursive parsers, i.e.

```
(parsecomb:define-parser r (either r (string "lol")))
```

will build a parser that never terminates.

<br/>

Have fun!
