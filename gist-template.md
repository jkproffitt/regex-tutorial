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

### Anchors

-   Anchors are unique in that they match a position within a string, not a character.

-   beginning ^ : Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled. This matches a position, not a character.

> Example: `^\w+`

-   end $ : Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.

> Example: `\w+$`

-   word boundary \b : Matches a word boundary position between a word character and non-word character or position (start / end of string).

> Example: `s\b`

### Quantifiers

Matches the specified quantity of the previous token. {1,3} will match 1 to 3. {3} will match exactly 3. {3,} will match 3 or more.

> Example: `b\w{2,3}`

### Grouping Constructs

Groups allow you to combine a sequence of tokens to operate on them together. Capture groups can be referenced by a backreference and accessed separately in the results.

-   capturing group (ABC) : Groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.

> Example: `(ha)+`

-   named capturing group (?<name>ABC) : Creates a capturing group that can be referenced via the specified name.

-   numeric reference \1 : Matches the results of a capture group.
    > For example \1 matches the results of the first capture group & \3 matches the third.: `(\w)a\1`

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

© 2023 [jkproffitt](https://github.com/jkproffitt/regex-tutorial). Confidential and Proprietary. All Rights Reserved.
