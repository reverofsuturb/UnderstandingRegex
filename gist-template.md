# Understanding Regex

This is a brief tutorial going over regex, short for regular expression, statements, which are a way of creating search patterns for matching text, providing us with a clear path of validation when it comes to user input. Using patterns which we create with regex statements we can also go through strings to find and replace characters as well as sequences.

## Summary
Code: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
We will be taking a look at a regex statement used to match an email and make sure that it is in an acceptable format. This could be used in a variety of ways, including validation for a user sign up on a website, or sifting through a large chunk of data and finding all email addresses within that.

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
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Anchors in regex expressions signify the beginning and end of strings within an expression. In our expression we see the `^` at the beginning as well as the `$` symbol at the end, these are our anchors, since we are looking for an e-mail this is capturing the whole statement as one.

### Quantifiers
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Quantifiers in regular expressions are used to set limits of strings that our regex statement is matching. Most frequently they include the minimum amount of characters and the maximum amount of characters that can be included. In our case, our quantifier is at the end of our statement `{2,6}` and is contained within parenthenses `([a-z\.]{2,6})` meaning that it will only target this substring. The quantifier in this statement is limiting the minimum amount of characters in this substring to 2, and the maximum amount of characters as 6.

### Grouping Constructs
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Grouping constructs are used to break up a string into substrings/subexpressions so that you can create multiple rulesets for one string. These are denoted by the parenthenses `( )` separating our expression into three groups. Each of these subexpressions have different rulesets which our regex is looking to match, another way to think of this which may be more clear is: `(ruleset)@(ruleset).(ruleset)` 

### Bracket Expressions
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`


### Character Classes
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### The OR Operator
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Flags
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Character Escapes
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
