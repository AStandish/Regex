# Regex

Regular expressions or Regex are simple characters or patterns of characters that are used in most programming languages. They are used match character combinations in strings which can save coder a lot of time when building web applications. In the language that we use most often in this bootcamp, Javascript, Regex are also objects.

## Summary

In this tutorial, I will be describing the following Regex: Anchors, Quantifiers, Grouping Constructs, Bracket Expressions, Character Classes, The OR Operator, Flags, and Character Escapes. I will use this snippet example: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/, which matches an e-mail address, to explain the different regex components. 

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
Regex components or character classes match one character. Those regex characters are considered literal. For example, W literally means a capital w or a m literally means lowercase m. Since they are literal components, they must be wrapped in slashes /. Lets review the snippet again: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. The components are listed below. 

### Anchors
Anchor regex are ^ and $. ^: you can match any string that begins with that character. For example, ^It, you can match a string that begins with It. In turn, $, matches any string that ends with that character. For example, boo$, will find a string that ends with boo. The match email snippet begins with ^([a-z0-9_\.-]+) so the regex would be looking for a string that begins with ([a-z0-9_\.-]+). It also ends ([\da-z\.-]+)\.([a-z\.]{2,6})$ and would be looking for a string that ends with ([\da-z\.-]+)\.([a-z\.]{2,6}). I'll explain the components within the parentheses below. 


### Quantifiers
Quatifier regex are * + ? and {}. * matches any string that contains the first two characters preceding it and also none of the third character or many of the third character. For example, bfg* matches all of these combinations: bf bfg bfgg fbfg. + matches any string that matches the string preceding it exactly how it is written. For example, bfg+ matches only the last 3 of these combinations: bf bfg bfgg fbfg. ? matches any string that contains the first two characters preceding it and also none of the third character or only one of the third character. For example, bfg* matches the first two and last, but not the third example, of these combinations: bf bfg bfgg fbfg. {} matches whichever parameters are defined within the {}. For example, bfg{2} matches a string of bf followed by 2 g's. bfg(3,) matches a string of bf followed by 3 or more g's. bfg{4,7} matches a string of bf followed by 4 to 7 g's. b(fg)* matches a string that has a followed by 0 or more copies of the occurance of fg. b(fg){4,7}  matches a string that has a followed by 4 up to 7 copies of the occurance of fg. In the email snippet, ^([a-z0-9_\.-]+) the + matches any string that has any letters a through z, any numbers 0 through 9, an underscore, period or hyphen. Also, ([\da-z\.-]+)\ the + here would match anything within the parantheses. ([a-z\.]{2,6} matches 2 to 6 characters that match the bracket expressions, ie domain names like us, com, edu, etc. 


### Grouping Constructs
Grouping contructs, (), is very useful when you need to match or find any information within a program. For example, b(tag) matches a string that contains any occurance of tag: btagb, bfgtag, blovetag. In the email snippet, ([a-z0-9_\.-]+) the parentheses would capture a match within its contents. 

### Bracket Expressions
Bracket Expressions, [], matches a string that contains anything within the bracket. For example, [bog] matches any string that has a b, o, or g within it. [b-g] would match any string that contains any letter b-g. If you use the character ^, it negates what is in the brackets. For example, [^bang] would not match any string containing b, a, n, g. Brackets are case sensitive. In the email snippet, ([a-z\.]{2,6}, it would be capturing letters from a through z.

### Character Classes
Anchor regex are ^ and $. ^: you can match any string that begins with that character. For example, ^It, you can match a string that begins with It. In turn, $, matches any string that ends with that character. For example, boo$, will find a string that ends with boo. The match email snippet begins with ^([a-z0-9_\.-]+) so the regex would be looking for a string that begins with ([a-z0-9_\.-]+). It also ends ([\da-z\.-]+)\.([a-z\.]{2,6})$ and would be looking for a string that ends with ([\da-z\.-]+)\.([a-z\.]{2,6}). I'll explain the components within the parentheses below. 
Anchor regex are ^ and $. ^: you can match any string that begins with that character. For example, ^It, you can match a string that begins with It. In turn, $, matches any string that ends with that character. For example, boo$, will find a string that ends with boo. The match email snippet begins with ^([a-z0-9_\.-]+) so the regex would be looking for a string that begins with ([a-z0-9_\.-]+). It also ends ([\da-z\.-]+)\.([a-z\.]{2,6})$ and would be looking for a string that ends with ([\da-z\.-]+)\.([a-z\.]{2,6}). I'll explain the components within the parentheses below. 
Character classes regex are \d \w \s and \. . \d matches a single character that is a digit. For example, matches \d f4df, r6babe, 8kill, 3for. \D matches a nondigit character. For example, \D would match for, three, boo, but not 45. \w matches any alphanumeric character. For example the following would match:\w babe, 453, b343j, but not ,.*&. \W matches a digit character. For example, \W matches 3456, but not four. \s matches any white space character including tabs and line breaks. For example,\s abc ac acb, the spaces between abc and ac, and the space between ac and acb would match. \S matches any nonwhitespace character. For example, \S matches 234 234 boo (the characters but not the space between them. \. matches any character, including letters, numbers, special characters, and white spaces. For example, \. 32k ?23k would all match. In the snippet example, ([\da-z\.-]+)\, \d matches a single character that is a digit. \. - Matches a single period (like that between ([\da-z\.-]+)\.([a-z\.]{2,6})$) the two sets of parenthesis ie the dot in .com. 

### The OR Operator
The OR Operator, |, matches a string that has a followed by the characters before and after | (and captures the characters before and after it.) For example, t(x|n) would match txn tn tnx but not thn.

### Flags
The flags in regex are g, m, i. g flag stands for global which means that the regex should be tested for matches against all possible strings and match all occurances of which you are looking for. For example, /hat/g would match every single occurance of hat in a string and not just the first occurance. m flag stands for multiline and would match multiple lines. For example, /^bf/  would match the first string that starts with bf, but /^bs/m would match a sting that begins with bs in multiple lines. The same would apply to $ but for the end of a string. i flag makes the whole regex case insensitive. For example, /KiT/i would mat KiT, kIt, kit, KIt, or Kit. 

### Character Escapes
The special regular expression characters for Javascript are  . \ + * ? [ ^ ] $ ( ) { } = ! < > | -.You can escape a special regex character by putting a backslash in front of it, for example, as we have discussed, ^ matches a character at the beginning of a string, but, \^ would interpret that character literally.

## Author

I'm a special education teacher, single Mommy, and an up and coming programmer. Here's a link to my github: https://github.com/AStandish
