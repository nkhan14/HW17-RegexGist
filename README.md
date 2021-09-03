# HW17-RegexGist | Regular Expressions

As a programmer, it is important to be able to identify and manipulate strings of text that we are interested in, like an email, a code, or a URL. We can do this by using regular expressions (also known as regex), which are sequences of characters that define a search pattern. Regular expressions are written in such a way that can be interpreted by regex processors, which can examine text and identify which parts match your regex search terms.

## Summary

In this gist, we will dive into the plethora of regex expressions. This gis will act almost as a cheatsheet for new programmers. This cheatsheet was created using https://www.regextester.com. 

## Table of Contents

- [Basic Syntax](#basic-syntax)
- [Position Matching](#position-matching)
- [Character Classes](#character-classes)
- [Special Characters](#special-characters)
- [Groups and Ranges](#groups-and-Ranges)
- [Quantifiers](#quantifiers)
- [Escape Sequences](#escape-sequences)
- [String Replacement](#string-replacement)
- [Assertions](#assertions)
- [POSIX](#POSIX)
- [8 REGULAR EXPRESSIONS YOU SHOULD KNOW](#8-regular-expressions-you-should-know)
- [Review](#review)

## Regex Components

### Basic Syntax

- `/.../`: Start and end regex delimiters
- `|`: Alternation
- `()`: Grouping

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

### Position Matching

- `^`: Start of string or start of line in multi-line mode
- `\A`: Start of string
- `$`: End of string or end of line in multi-line mode
- `\Z`: End of string
- `\b`: Word boundary
- `\B`: Not word boundary
- `\<`: Start of word
- `\>`: End of word

### Character Classes

- `\s`: Whitespace
- `\S`: Not whitespace
- `\w`: Word
- `\W`: Not word
- `\d`: Digit
- `\D`: Not digit
- `\x`: Hexade­cimal digit
- `\O`: Octal digit

### Special Characters

- `\n`: Newline
- `\r`: Carriage return
- `\t`: Tab
- `\v`: Vertical tab
- `\f`: Form feed
- `\xxx`: Octal character xxx
- `\xhh`: Hex character hh


### Groups and Ranges

- `.`: Any character except newline (\n)
- `(a|b)`: a or b
- `(…)`: Group
- `(?:…)`: Passive (non-c­apt­uring) group
- `[abc]`: a, b or c
- `[^abc]`: Not a, b or c
- `[a-z]`: Letters from a to z
- `[A-Z]`: Uppercase letters from A to Z
- `[0-9]`: Digits from 0 to 9

> Note: Ranges are inclusive.

### Quantifiers

- `*`: 0 or more
- `+`: 1 or more
- `?`: 0 or 1
- `{3`: Exactly 3
- `{3,}`: 3 or more
- `{3,5}`: 3, 4 or 5

> Note: Quantifiers are greedy - they match as many times as possible. Add a ? after the quantifier to make it ungreedy.


### Escape Sequences

- `\`:Escape following character. Used to escape any of the following metacharacters: {}[]()^$.|*+?\.
- `\Q`: Begin literal sequence
- `\E`: End literal sequence


### String Replacement

- `$1`: 1st group
- `$2`: 2nd group
- `$n`: nth group
- `$'`: After matched string
- `$+`: Last matched string
- `$&`: Entire matched string

> Note: Some regex implem­ent­ations use \ instead of $.


### Assertions

- `?=`: Lookahead assertion
- `?!`: Negative lookahead
- `?<=`: Lookbehind assertion
- ``?!=, ?<!``: Negative lookbehind
- `?>`: Once-only subexp­ression
- `?()`: Condition if-then
- `?()|`: Condition if-then-else
- `?#`: Comment


### POSIX

- `[:upper:]`: Uppercase letters
- `[:lower:]`: Lowercase letters
- `[:alpha:]`: All letters
- `[:alnum:]`: Digits and letters
- `[:digit:]`: Digits
- `[:xdigit:]`: Hexade­cimal digits
- `[:punct:]`: Punctu­ation
- `[:blank:]`: Space and tab
- `[:space:]`: Blank characters
- `[:cntrl:]`: Control characters
- `[:graph:]`: Printed characters
- `[:print:]`: Printed characters and spaces
- `[:word:]`: Digits, letters and underscore


### Pattern Modifiers

- `g`: Global match
- `i`: Case-i­nse­nsitive
- `m`: Multi-line mode. Causes ^ and $ to also match the start/end of lines.
- `s`: Single-line mode. Causes . to match all, including line breaks.
- `x`: Allow comments and whitespace in pattern
- `e`: Evaluate replac­ement
- `U`: Ungreedy mode

### 8 REGULAR EXPRESSIONS YOU SHOULD KNOW:

- Matching a Username: `/^[a-z0-9_-]{3,16}$/`
- Matching a Password: `/^[a-z0-9_-]{6,18}$/`
- Matching a Hex Value: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`
- Matching a Slug: `/^[a-z0-9-]+$/`
- Matching an Email: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
- Matching a URL: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`
- Matching an IP Address: `/^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$/`
- Matching an HTML Tag: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

### Review

With all of this information in mind, go over this code and break it down:

regex: `([12]\d{3}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01]))`


-   1st Capturing Group ([12]\d{3}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01]))
        - Match a single character present in the list below [12]
        - 12 matches a single character in the list 12 (case sensitive)
        - \d matches a digit (equivalent to [0-9])
        - {3} matches the previous token exactly 3 times
        - matches the character - with index 4510 (2D16 or 558) literally (case sensitive)

-   2nd Capturing Group (0[1-9]|1[0-2])
        - 1st Alternative 0[1-9]
        - 0 matches the character 0 with index 4810 (3016 or 608) literally (case sensitive)
        - Match a single character present in the list below [1-9]
        - 1-9 matches a single character in the range between 1 (index 49) and 9 (index 57) (case sensitive)
        - matches the character - with index 4510 (2D16 or 558) literally (case sensitive)

-   3rd Capturing Group (0[1-9]|[12]\d|3[01])
        - 1st Alternative 0[1-9]
        - 0 matches the character 0 with index 4810 (3016 or 608) literally (case sensitive)
        - Match a single character present in the list below [1-9]
        - 1-9 matches a single character in the range between 1 (index 49) and 9 (index 57) (case sensitive) 

This should match that to: `1978-12-20`. I could be wrong, but I hope not :) !

## Author

My name is Nabiha Haleema Khan, I am a full stack web development bootcamp student along with being a full-time Field Applications Scientist at S2 Genomics. I took this course to learn code, so I can incorporate it in my field of science. 