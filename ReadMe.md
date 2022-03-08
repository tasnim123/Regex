# Computer Science for JavaScript: Regex Tutorial

## What Is a Regex?

A **regex**, which is short for **regular expression**, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input. 


## Summary

 A better understanding of different parts of regular expression and how to identify the different components that make up a regex.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [The OR Operator](#the-or-operator)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors don't check any of the characters. Instead, they match a character's position before or after it. The characters `^` and `$` are both recognized to be anchors.

- The caret `^` anchor corresponds to the text's start.
- The dollar `$` anchor corresponds to the text's end.

### Example:

**Code**

`let string = 'Hello';
console.log(/^H/.test(str));`

**Output**

True


The /^H/ match any text that starts with the letter H. It alaways returns true.

**Code**

`let string = 'Hello';
console.log(/^h/.test(string));`

**Output**

False


**Note:** It returns false because anchors are case sensitive.

**Code**

`let string = 'Hello';
console.log(/o$/.test(string));`

**Output**

True


The /o$/ match any text that end with the letter o. It alaways returns true.

### Quantifiers

Quantifiers are used to match a string's multiple instances of a character, group, or character class. The minimum and maximum number of characters that your regex is looking for are frequently included.

Quantifiers are as follow:

- `*` Matches the previous element zero or more times.
- `+` Matches the previous element zero or more times.
- `?` Matches the previous element zero or one time.
- `{x}` Matches the previous element exactly x times.
- `{x,}` Matches the previous element exactly x or more times.
- `{x,y}`  Matches the previous element between x and y times.

### Example:

**Code:**

`let string = "Hello for 123 Hello";
 let check = /Hello(?!123)/g;
 console.log(string.match(check));`

**Output:**

2


It returns 2 because in string hello is 2 times.

### Bracket Expressions

There are 3 types of brackets
- [] square brackets
- {} curly brackets
- () Parentheses

### [] square brackets

Brackets denote a set of characters that must be matched. Any character between the brackets will match, and you can also define a set with a hyphen.

`'cat'.match(/[abc]/) // -> matches 'ca'`

You will frequently see alphabetic ranges or all numerals. [A-Z, a-z] [0-9] Unless the I flag is set, keep in mind that these character sets are case sensitive.

`'dog'.match(/[a-d]/) // -> matches 'd'`
`'dog'.match(/[A-D]/i) // -> matches 'd'`

### { } Curly braces

Curly braces are used to specify a precise number of items that must match. They're used after an expression: \na{3}\  will only ever match 'na' thrice.

`'banana'.match(/na{2}/) // -> matches 'nana'`

### ( ) Parentheses

Matches are indicated by parentheses. This is particularly useful for find-and-replace operations or any time you need to work with a portion of a match. When you remember a match, you can refer to it with $n, which ranges from $1 to $9, or $&, which refers to the entire match.

`'John Smith'.match(/([A-Za-z]+)\s([A-Za-z]+)/) // -> matches 'John Smith' with 'John' remembered as $1 and 'McLastname' as $2`

`'John Smith'.match(/([A-Za-z]+)\s([A-Za-z]+)/, '$1') // ->
returns 'John'`

In regex, parentheses are also used to group parts of an expression into subgroups, as in /($|)([0-9]+).([0-9]2)/. This would match '$129.99' and keep the subgroups '$, 129, and 99' in mind. But what if you don't want to keep the dollar sign in your head?  `?:` is a valid option.

`'¥6000.50'.match(/(?:\$|¥)([0-9]+)\.([0-9]{2})/) // --> matches '¥6000.50' but only remembers '6000' as $1 and '50' as $2`

### The OR Operator

In regular expression, the term "alternation" is actually a simple "OR." It's represented by the vertical line character `|` in a regular expression.

**Code**

`let check = /html|css|java(script)?/gi;
let str = "HTML, CSS and JavaScript";
console.log( str.match(check) );`

**Output:**

'HTML', 'CSS', 'JavaScript'

### Character Escapes

Let's pretend we're looking for a dot. Just a dot, not "any character." Prefix a special character with a backslash to use it as a regular one. This is also known as "escape from a character."

### Example

`console.log( "Ch2.1".match(/\d\.\d/) ); -> 2.1 (match)`

`console.log( "Ch 211".match(/\d\.\d/) ); -> null (looking for a real dot \.)`

## Author
Tasnim Rahat github: https://github.com/tasnim123