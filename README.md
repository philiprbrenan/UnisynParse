# Unisyn expressions.

![Test](https://github.com/philiprbrenan/UnisynParse/workflows/Test/badge.svg)

Once there were many different character sets that were unified by [Unicode](https://en.wikipedia.org/wiki/Unicode). 
Today we have many different programming languages, each with a slightly
different syntax from all the others. The multiplicity of such syntaxes imposes
unnecessary burdens on users and language designers.  [UniSyn](https://github.com/philiprbrenan/UnisynParse) is proposed as a
common syntax that is easy to understand yet general enough to be used by many
different programming languages.

## The advantages of having one uniform language syntax:

- less of a burden on users to recall which of the many syntax schemes in
current use is the relevant one for the programming language they are currently
programming in.  Rather like having all your electrical appliances work from
the same voltage electricity rather than different voltages.

- programming effort can be applied globally to optimize the parsing [process](https://en.wikipedia.org/wiki/Process_management_(computing)) to
produce the fastest possible parser with the best diagnostics.

## Special features

- Expressions in Unisyn can be parsed in situ - it is not necessary to reparse
the entire source [file](https://en.wikipedia.org/wiki/Computer_file) to syntax check changes made to the [file](https://en.wikipedia.org/wiki/Computer_file). Instead
changes can be checked locally at the point of modification which should make
writing a syntax checking editor for Unisyn easier.

- Expressions in [UniSyn](https://github.com/philiprbrenan/UnisynParse) can be parsed using [SIMD](https://www.officedaytime.com/simd512e/) instructions to make parsing
faster than otherwise.

## Dyadic operator priorities
 [UniSyn](https://github.com/philiprbrenan/UnisynParse) has only four levels of dyadic operator priority which makes it easier
to learn. Conversely: [Perl](http://www.perl.org/) has 25 levels of operator priority.  Can we really
expect users to learn such a long list?

```
??????????????????????????????????????????????????????????

Assign: ????????????????????????
  Term
    Variable: ????
  Term
    Dyad: ????????????????
      Term
        Variable: ????
      Term
        Dyad2: ??
          Term
            Variable: ????
          Term
            Variable: ????

variable
variable
dyad2
variable
dyad
variable
assign
```

The priority of a dyadic operator is determined by the [Unicode Mathematical Alphanumeric Symbols](https://en.wikipedia.org/wiki/Mathematical_Alphanumeric_Symbols) that is used to
encode it.

The new operators provided by the [Unicode](https://en.wikipedia.org/wiki/Unicode) standard allows us to offer users a
wider range of operators and brackets with which to express their intentions
clearly within the three levels of operator precedence provided.

## Lexical elements

### Ascii.

Printable ASCII characters not including space, [tab](https://en.wikipedia.org/wiki/Tab_key) or new line.

Contains: 146 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ! | " | # | $ | % | & | ' | ( | ) | * | + | , |  | . | / | 0 |
 | 1 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | : | ; | < | = | > | ? | @ |
 | 2 | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P |
 | 3 | Q | R | S | T | U | V | W | X | Y | Z | [ | \ | ] | ^ | _ |  |
 | 4 | a | b | c | d | e | f | g | h | i | j | k | l | m | n | o | p |
 | 5 | q | r | s | t | u | v | w | x | y | z | { |  | } | ~ | ??? | ??? |
 | 6 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 7 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 8 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 9 | ??? | ??? |


### Assign.

Assign [infix](https://en.wikipedia.org/wiki/Infix_notation) operator with right to left binding at priority 2.

Contains: 221 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 7 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 8 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 9 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | a | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | b | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | c | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | d | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |


### Dyad.

Infix operator with left to right binding at priority 3.

Contains: 110 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 1 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 2 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 3 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 4 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 5 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 6 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |


### Dyad2.

Infix operator with left to right binding at priority 4.

Contains: 1907 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ?? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 7 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 8 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 9 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | a | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 10 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 11 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 12 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 13 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 14 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 15 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 16 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 17 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 18 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 19 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1a | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 1f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 20 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 21 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 22 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 23 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 24 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 25 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 26 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 27 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 28 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 29 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2a | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 2f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 30 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 31 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 32 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 33 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 34 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 35 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 36 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 37 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 38 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 39 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ???? | ???? |
 | 3a | ?? | ?? | ?? | ?? | ?? | ?? | ?? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 3f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 40 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 41 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 42 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 43 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 44 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 45 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 46 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 47 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 48 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 49 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4a | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 4f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 50 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 51 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 52 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 53 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 54 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 55 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 56 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 57 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 58 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 59 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5a | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 5f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 60 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 61 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 62 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 63 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 64 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 65 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 66 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 67 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 68 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 69 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6a | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6b | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6c | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6d | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6e | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 6f | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 70 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 71 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 72 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 73 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 74 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 75 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 76 | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? | ??? |
 | 77 | ??? | ??? | ??? |


### Prefix.

Prefix operator - applies only to the following variable or bracketed term.

Contains: 110 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 1 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 2 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 3 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 4 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 5 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 6 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |


### Suffix.

Suffix operator - applies only to the preceding variable or bracketed term.

Contains: 110 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 1 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 2 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 3 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 4 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 5 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 6 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |


### SemiColon.

Infix operator with left to right binding at priority 1.

Contains: 1 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ??? |


### Variable.

Variable names.

Contains: 110 characters.


 |  | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | A | B | C | D | E | F |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
 | 0 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 1 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 2 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 3 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 4 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 5 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |
 | 6 | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? | ???? |




## Minimalism through Unicode

This [module](https://en.wikipedia.org/wiki/Modular_programming) is part of the Earl Zero project: using Perl 5 to create a minimal,
modern [Unicode](https://en.wikipedia.org/wiki/Unicode) based programming language: Earl Zero. Earl Zero generates x86 [assembler](https://en.wikipedia.org/wiki/Assembly_language#Assembler) [code](https://en.wikipedia.org/wiki/Computer_program) directly from a [program](https://en.wikipedia.org/wiki/Computer_program) consisting of a single Unisyn expression
with no keywords; only expressions constructed from [user](https://en.wikipedia.org/wiki/User_(computing)) defined
[unary](https://en.wikipedia.org/wiki/Unary_operation) and
[binary](https://en.wikipedia.org/wiki/Binary_operation)
[operators](https://en.wikipedia.org/wiki/Operator_(mathematics)) are used to
construct Unisyn [programs](https://en.wikipedia.org/wiki/Computer_program). 
Minimalism is an important part of Earl Zero; for example, the "Hello World" [program](https://en.wikipedia.org/wiki/Computer_program) is:

```
Hello World
```

Earl Zero leverages Perl 5 as its [macro
assembler](https://en.wikipedia.org/wiki/Assembly_language#Macros) and
[CPAN](https://metacpan.org/author/PRBRENAN) as its [module](https://en.wikipedia.org/wiki/Modular_programming) repository.

## Other languages
 [Lisp](https://en.wikipedia.org/wiki/Lisp), [Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)), [Tcl](https://en.wikipedia.org/wiki/Tcl) are well known, successful languages that use generic syntaxes.

## Join in!

Please feel free to join in with this interesting project - we need all the [help](https://en.wikipedia.org/wiki/Online_help) we can get.
