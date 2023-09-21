---
layout: post
title: Regex Essentials
date: 2020-09-09 13:32:20 +0300
description: Regex Essentials
img: i-regex.png
fig-caption: # Add figcaption (optional)
tags: [regex, regex-intro]
---
## Regex Essentials
Regex, short for Regular Expressions, is a powerful tool for pattern matching and text manipulation. It's widely used in programming, data extraction, and text processing tasks. In this guide, we'll explore essential regex components, including anchors, quantifiers, character classes, flags, grouping, and the often-mysterious \b word boundary.

### Aanchors:

1. #### `^`: The Beginning Anchor
  The `^` symbol matches the beginning of a line or string.
  
2. #### `$` : - The End Anchor
  The `$` symbol matches the end of a line or string.
 
 Example : ^The end$ : matches "The end"
 
### Quantifiers:
 
1. #### `*` : Zero or More Occurrences
   This matches zero or more occurrences
2. #### `+` : One or More Occurrences
   This matches one or more occurrences
3. #### `?` : Zero or One Occurrence
   This matched zero or one occurence
4. #### `{number}` : Specific Number of Occurrences
   This matches "number" of times occurenes
5. #### `{number, }` : "Number" or More Occurrences
   This matches "number" of times to more occurenes
6. #### `{number1, number2}` : Range of Occurrences
   This matches "number1" of times to "number2" of times occurenes
7. #### `(text)` :  Grouping
   followed by "text"
   
### OR operator
1. #### `| or []`: Alternation
    1. `a(b|c)` 
       - This matches a followed by b or c
    2. `a[bc]`
       - This matches a followed by b or c

### Character classes
1. #### `\d` : Digit
   matches a single digit
2. #### `\w` : Word Character
   matches a word character including underscore
3. #### `\s` : Whitespace
   matches a whitespace character, tabs, line breaks
4. #### `.` : Any Character
   matches any character
> 1. `\D`, `\W`, `\S` are there as their negations.
> 2. To match special characters like : `^, $, *, +, ?, (, ), {, |, }, [, ]` you need to escape them with a `\`.

### Flags
Regex patterns typically appear between / symbols and can have flags at the end:
 1. `/g` (global): Continues matching after the first match, restarting the search.
 2. `/m` (multi-line): Matches the start and end of lines with '^' and '$'.
 3. `/i` (insensitive): Makes the expression case-insensitive.
 
### Grouping
 1. #### `()`: Capturing Group
    this creates a capturing group.
 2. #### `?`: inside the patantesis ex: (?:chars)
    this disables the capturing group
 3. #### `?<name>` : Named Group
    this puts a name to the group
 > `*` (zero or more occurrences), `+` (one or more occurrences), and `{}` are called greedy operatoers as they match as far as then can. 
 
 
### \btext\b : Word Boundaries
 1. \btext\b acts as a boundary matcher, similar to ^ and $, ensuring precise word-based matches.

Regex is a versatile tool that can greatly simplify text manipulation tasks. Understanding these fundamental regex elements will empower you to leverage its capabilities effectively.
