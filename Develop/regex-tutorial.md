# Regex-Tutorial for matching an Email
This tutorial was created to help with understanding how regular expressions (regex), uses a series of special characters to look for a specific pattern to match in text. It can be used in many programming languages and applications. It can perform complex search-and-replace operations, can look for specific data from strings, as well as validate input.

## Summary
In this tutorial, we will use the pattern 
* `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` 
to match and validate any email address. Let's cover some key components that is used to create an expression.

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
Anchors in regular expressions are used when trying to match positions within a string rather than matching a special character. 
Primary anchors used are `^`, `$`,`\b`, and `\B`. We will go over the components from our example.

- This is called a Caret `^` and is used to start the string. It represents a string that starts with the characters that follow it.  
- The `$` dollar sign is used to match the end of the string and represents a string that ends with the characters that follow it.
  
### Quantifiers
In regular expressions, quantifiers are metacharacters that indicate how many times a character, group, or character class should be repeated in the input for a match to be found.
Quantifiers cannot appear alone and are used to specify a minimum and a maximum number of times your pattern must repeat. 

Some primary quantifiers include `*`, `+`,`?`, `{n}`, `{n,}`, `{n,m}`.

-In our regex example, `+` means one or more of the previous character. It basically confirms that there is at least one of the characters present, but there can also be many more. In this case, 
it looks for a pattern from `a`-`z`, numbers from `0`-`9` and special characters of `_`,`.`, `-`. 

-`{n,m}` specifies a range of characters that the previous element has to match, which means that the element must be present at least `n` times and at most `m` times.
In this case, the `{2,6}` allows a pattern to match a minimum of 2 characters and maximum of 6 characters in the domain name. 

### Grouping Constructs
Grouping Constructs define a group of characters that are listed inside a parenthesis `()`, which are matched and then can be referenced later. In this expression, we have 3 groups.

-The first group consists of `([a-z0-9_\.-]+)`, and is used to capture the email's username, which allows the username to include at least one character from `a-z`, numbers between `0-9` or include special characters 
like `_`,`.`, `-`.

-The second group consists of `([\da-z\.-]+)` after the `@`, and is used to capture the second-level domain like `yahoo` or `gmail` etc. 
In this expression, it is allowed to include at least one character from `a-z`, numbers between `0-9` or include special characters 
like `_`,`.`, `-`. 

-The third group consists of `([a-z\.]{2,6})`, which is used to capture the top-level domain name like `.com`. In this expression, it is allowed to include characters from `a-z`, 
but must contain a minimum of 2 and a maximum of 6 alphabetical characters `{2,6}`.

### Bracket Expressions
Bracket expressions, also known as positive character group, are characters that are listed inside a set of square brackets ([]). These bracket expressions are used to match any single character or a range of characters. 
You can use a hyphen (-) to define a set of characters inside the brackets, or simply have an individual character to match. 

In this expression, there is `[a-z0-9_\.-]`, which allows characters from `a-z`, numbers
between `0-9`, or special characters like `_`,`.`, `-`.

### Character Classes
Character classes are used to specify only one character that can be matched out of many characters inside the brackets ([]). You can specify which character you want to match out of a range of characters by listing them inside square brackets ([]). By using a hyphen (-), you can determine a range of characters.
For example in this expression, `[0-9]`, a single digit between `0-9` is allowed to match.

### The OR Operator
The `OR` operator `|`, also known as the "alteration operator", allows you to provide alternatives within a pattern to be matched. For example `(blue|red|purple|yellow)`, allows you to match one of those colors provided. 
In the expression used in this tutorial, no OR operator was used.

### Flags
Flags are used to modify the default search behavior of a regular expression. They are optional parameters that change the pattern behavior. They are placed at the end of the expression, after the second forward slash `/abc/i`. 
Using flags, will allow you to control various aspects of matching, such as ignoring case sensitivity, global searching, multiline searches and more.

For example:

-`i` --> Case-insensitive, which allows the expression to match both lowercase and uppercase characters, regardless of their case.

-`g` --> Global search, which allows the expression to search for all matches in the string, rather than stop after the first match. 

-`m` --> Multiline mode, changes the behavior of the `^` and `$` anchors. It matches the start and end of each line within the string. Not using the `m` flag, will match the start 
and end of the entire string instead. 

### Character Escapes
In regular expressions, character escapes are used to indicate characters that have special meaning, or represent characters that might not be able to respresent in its literal form. Escaping these characters let's you include them in your pattern. You have to use a backslash (/) in front of the 
character that you would like to literally search. 

Some common character escapes include:

- `\f` --matches a form feed character.
- `\n` --matches a newline character.
- `\r` --matches a carriage return character.
- `\t` --matches a tab character.
- `\v` --matches a vertical tab character.
- `\0` --matches a null character.
- `\'` --matches a single quote character.
- `\"` --matches a double quote character.

## Author
If you have questions, please feel free to contact me [Agrig33](https://github.com/Agrig33). 