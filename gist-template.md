# Email Regular Expression Tutorial

The purpose of this tutorial is to show how an email Regular Expression (RegEx) works. In this example we will be using a RegEx designed to grab email match email adresses. To do so we will break down the individual components of the RegEx to better understand how it works as a whole.

## Summary

In this tutorial we will learn how to match an Email using the following regex: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Table of Contents

-   [Anchors](#anchors)
-   [Quantifiers](#quantifiers)
-   [Grouping Constructs](#grouping-constructs)
-   [Bracket Expressions](#bracket-expressions)
-   [Character Classes](#character-classes)
-   [The OR Operator](#the-or-operator)
-   [Flags](#flags)
-   [Character Escapes](#character-escapes)

## Regex Components

Regexes are composed of several different components that work together to define a search pattern. The most common components include the ones listed below.

The most common syntax elements include:

Backslash `\` : Escapes special characters and allows them to be used as literal characters.
Brackets `[]` : Defines a set of characters to be matched.
Parentheses `()` : Captures part of a match into a group.
Asterisk `*` : Matches zero or more occurrences of the preceding character or character class.
Plus sign `+` : Matches one or more occurrences of the preceding character or character class.
Question mark `?` : Matches zero or one occurrences of the preceding character or character class.
Pipe `|` : Used to match either of two characters or character classes.

### Anchors

-   Anchors are unique in that they match a position within a string, not a character.

-   beginning `^` : Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled. This matches a position, not a character.

    > Example: `^\w+`

-   end `$` : Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

    > Example: `\w+$`

-   word boundary `\b` : Matches a word boundary position between a word character and non-word character or position (start / end of string).
    > Example: `s\b`

### Quantifiers

Matches the specified quantity of the previous token. {1,3} will match 1 to 3. {3} will match exactly 3. {3,} will match 3 or more.

> Example: `b\w{2,3}`

### Grouping Constructs

Groups allow you to combine a sequence of tokens to operate on them together. Capture groups can be referenced by a backreference and accessed separately in the results.

-   capturing group `(ABC)` : Groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.

    > Example: `(ha)+`

-   named capturing group `(?<name>ABC)` : Creates a capturing group that can be referenced via the specified name.

-   numeric reference \1 : Matches the results of a capture group.
    > For example \1 matches the results of the first capture group & \3 matches the third.: `(\w)a\1`

### Bracket Expressions

Bracket expressions can be used to match a single character or collating element.

-   `[abcd]` Matches any character in the square brackets.

> Example: `gr[ae]y` matches both spellings of the word 'grey'; that is, gray and grey.

-   `[a-d]` Matches any character in the range of characters separated by a hyphen (-).

> Example: `[0-9]` matches any decimal digit.
> and `[ab3-5]` matches a, b, 3, 4, and 5.

-   `[^abcd]` or `[^a-d]` Matches any character except those in the square brackets or in the range of characters separated by a hyphen (-).
    > Example: '[^0-9]' matches any string that does not contain any numeric characters.

### Character Classes

Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets.

-   character set `[ABC]` : Match any character in the set.

    > Example: `[aeiou]`

-   negated set `[^ABC]` : Match any character that is not in the set.

    > Example: `[^aeiou]`

-   range `[A-Z]` : Matches a character having a character code between the two specified characters inclusive.

    > Example: `[g-s]`

-   dot `.` : Matches any character except linebreaks. Equivalent to [^\n\r].

### The OR Operator

`|` represents the OR operator; which is used to include the number 0.

> Example : `(gif|png|jpg|jpeg)` matches either "gif", "png", "jpg" or "jpeg". The `|` denotes "OR" operator. The parentheses are used for grouping the selections.

### Flags

Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression (ex. `/.+/igm` ).

-   ignore `i` : Makes the whole expression case-insensitive.

    > For example: `/aBc/i` would match AbC.

-   global search `g` : Retain the index of the last match, allowing subsequent searches to start from the end of the previous match.

    > Note: Without the global flag, subsequent searches will return the same match.

-   multiline `m` : When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
    > Note that patterns such as /^[\s\S]+$/m may return matches that span multiple lines because the anchors will match the start/end of any line.

### Character Escapes

Escape sequences can be used to insert reserved, special, and unicode characters. All escaped characters begin with the \ character.

-   reserved characters `\+` : The following characters have special meaning, and should be preceded by a \ (backslash) to represent a literal character: `+*?^$\.[]{}()|/`
    > Example: `\+`

Within a character set, only \, -, and ] need to be escaped.

-   control character escape `\cI` : Escaped control character in the form \cZ. This can range from `\cA` (SOH, char code 1) to `\cZ` (SUB, char code 26)`.
    > Example : \cI matches TAB (char code 9).

#### Escaped Characters

For convenience, these escaped characters are supported in the Replace string in RegEx: \n, \r, \t, \\, and unicode escapes \uFFFF.

## Author

© 2023 [jkproffitt](https://github.com/jkproffitt/regex-tutorial). Confidential and Proprietary. All Rights Reserved.
