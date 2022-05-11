# RegEx Tutorial

## Matching a Hex Value

I am a softare student working on full stack applications, this is a gist I've made that explains one regex expression. They can be very confusing so I broke it down to help myself gain a better understanding.

## Summary

This regex expression will check for hex values. Below each part of the expression is broken down in depth.

> Matching a Hex Value: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

In regular expressions different anchors mean different things. Anchors do not match any characters, they match a position before or after characters. For example...

> console.log(/b$/.test('bob'));

would return 'true' because the string 'bob' ends with a 'b'.
On the other hand, '^' matches the beginning of the text.

> console.log(/^R/.test('Bob'));

would return 'false' because Bob does not start with a B.

The ^ anchor signifies the string that begines with the characters that follow.

### Quantifiers

Quantifiers indicate numbers of characters or expressions to match.For Example.

> o{2}

looks for exactly 3 occurences of the previous item 'a'. for example the word 'food' would be a match because it has two 'o's next to eachother, the word 'Top' would not match. Another type of quantifiers are known as the 'greedy' quantifiers. They attempt to match as much of the string as possible UNLESS you add a ? after. IF this is added the quanitfier will stop as soon as it finds a match. For example...

> /<.\*>/ will match '<hello> <world>'

with a question mark added...

> /<.\*?>/ will only match '<hello>' because it stops after one match.

In hex value matcher the quantifier is the '?' indicating that the '#' is optional. it is optional for the '#' to match.

### Grouping Constructs

Groups and ranges indicate groups and ranges of expression characters.
For example in the hex value matches the '-' groups the characters inside

for example

> [xyz] | [x-z]

would both match.

### Bracket Expressions

Bracket expressions use

> [ ]

to indicate a range of characters that we want to match. for example
in the above expression the bracket expressions are looking for either the letters a-f or numbers 0-9.

> [a-f0-9]

### Character Classes

a character class is a bracket expression that matches any of the characters inside the brackets.
In the Hex value matcher it is used to check numbers and letters between specific ranges. For example...

> [a-f0-9]

is looking for the letters 'a' through 'f' and the numbers '0' through '9'.

### The OR Operator

the | operater means 'either/or' as far as matching values is concerned. Inside a group it will act as an or between other matching conditions. For example

> x|y

would match either 'x' or 'y'.
In the hex value matcher the '|' operator says that if either of the two conditions...

> /^#?([a-f0-9]{6} or [a-f0-9]{3})$/

are met, that item will be a match for this statement.

### Flags

Regular expressions can use flags that impact the search. There are only 6 of them in JavaScript. for example.

> ?nO matches 'no'

where if would not match were the flag not there.

in the hex value matcher '?' in the first condition makes a-f case insensitive.

### Character Escapes

character escapes are things that seperate whatever you are passing as regex, for example if you were looking to match '(' instead of grouping with that same '(' you woud input...

> /(/

in this example the 'escape' is the '/' that is before and after the entire expression.

## Author

I am the author Brennan Heley thanks for reading my tutorial! I hope that cleared up some confusion.If you would like to see some of my coding work take a look at my [github](https://github.com/brennan64).
