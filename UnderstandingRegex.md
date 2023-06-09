# Understanding Regex

This is a brief tutorial going over regex, short for regular expression, statements, which are a way of creating search patterns for matching text, providing us with a clear path of validation when it comes to user input. Using patterns which we create with regex statements we can also go through strings to find and replace characters as well as sequences.

## Summary
We will explore regex statements by looking at this expression: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
This regex statement can be used to match an email and make sure that it is in an acceptable format. This could be used in a variety of ways, including validation for a user sign up on a website, or sifting through a large chunk of data and finding all email addresses within that.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Putting it All Together](#putting-it-all-together)

## Regex Components

### Anchors
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Anchors in regex expressions signify the beginning and end of strings within an expression. In our expression we see the `^` at the beginning as well as the `$` symbol at the end, these are our anchors, since we are looking for an e-mail this is capturing the whole statement as one. The `/` at the beginning and the end of our statement are not anchors, regex expressions are literals and need to be wrapped with these. 

### Quantifiers
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Quantifiers in regular expressions are used to set limits of strings that our regex statement is matching. Most frequently they include the minimum amount of characters and the maximum amount of characters that can be included. In our case, our quantifier is at the end of our statement `{2,6}` and is contained within parenthenses `([a-z\.]{2,6})` meaning that it will only target this substring. The quantifier in this statement is limiting the minimum amount of characters in this substring to 2, and the maximum amount of characters as 6. We also have a few `+` quantifiers in our statement, these indicate that the preceding statement must match one or more of the conditions. We see these quantifiers at the end of the bracket expressions within our first two subexpressions. 

### Grouping Constructs
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Grouping constructs are used to break up a string into substrings/subexpressions so that you can create multiple rulesets for one string. These are denoted by the parenthenses `( )` separating our expression into three groups. Each of these subexpressions have different rulesets which our regex is looking to match, another way to think of this which may be more clear is: `(ruleset)@(ruleset).(ruleset)` 

### Bracket Expressions
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Bracket expressions are the patterns inside of the square brackets `[ ]` and represent ranges of characters that we want our regex expression to match. In our expression we have three separate bracket expressions.
- `[a-z0-9_\.-]` <br>
 `a-z` this is matching all lowercase characters in a range of a through z <br>
 `0-9` is matching all numbers from 0 through 9 <br>
 `_\.-]+` here we are matching `_`, `.`, and `-` symbols, the backslash signifies an [escaped character](#character-escapes) which we will go over later in this tutorial <br>

- `[\da-z\.-]` <br>
`\d` is another way of writing 0-9, this matches any Arabic numeral digit <br>
 `a-z` is matching all lowercase characters in a range of a through z <br>
 `\.-` matches `.` and `-` symbols <br>
- `[a-z\.]` this is matching all lowercase characters in a range of a through z as well as the `.` symbol

### Character Classes
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Character classes are built in to regex expressions to define sets of characters in bracket expressions. The ranges that we use for matching within our bracket expressions are also considered character classes i.e. `[a-z] [0-9]`
When we use `\d` in our second subexpression this is one of the built in ranges, this one in particular represents all numerical Arabic digits. 

### The OR Operator
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

We are not using the OR operator in our expression which is denoted using `|`. The OR operator is used most often to used outside of bracket expressions, lets say you want to match `(example123)` will match only to `example123` , by adding the OR operator `(example|1|2|3)` this expression will now match `example` by itself or with any combination of `1, 2, 3` 


### Flags
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

We are not using flags in our expression. Flags are used at the end of a statement after the ending `\`. These will define additional functionality and limits of the expression, for example in `/[a-z]/i` we are using the `i` flag so that this expression matches lowercase and uppercase a through z, because the flag makes it case insensitive

### Character Escapes
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Character escapes in regex expressions are used to "escape" characters which changes the interpretation of the character typically taking away it's significance/functionality. In our expression we are using two different character escapes `\.` and `\d`, without escaping these characters, `.` would match any character except newline characters, and `d` would match `d`. 

### Putting it All Together
```regex
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

Let's put everything together:
- `/^` we begin our statement and indicate the beginning of our string <br>
-  `([a-z0-9_\.-]+)` this is our first capture group, this group matches lowercase characters a-z, numbers 0-9, and the `_` `.` and `-` symbols, one or more must match <br>
- `@` this must match an `@` symbol <br>
- `([\da-z\.-]+)` this is our second capture group, this group matches lowercase characters a-z, numbers 0-9, and the `.` and `-` symbols, one or more must match <br>
- `\.` this must match a `.` symbol <br>
- `([a-z\.]{2,6})` this is our third capture group, this matches lowcase characters a-z and the `.` symbol, limits of a minimum of 2 and maximum of 6 characters have been placed <br> 
- `$/` we end our statement and indicate the end of our string <br>

And there we go, that's what our regex statement will do!

## Author
I am currently student aspiring to be a developer.
If you wish to contact me or have additional questions you can reach me at either my [github profile](https://github.com/reverofsuturb) or feel free to email me at [sfriedman6711@gmail.com](mailto:sfriedman6711@gmail.com)
