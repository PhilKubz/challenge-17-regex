# Regex Tutorial: Matching an Email


## Summary

In this tutorial, we are going to take a look at the regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` and demonstrate how it can be used to match email addresses. When breaking down the components of the regex expression, we will explain its functionality and provide examples to demonstrate its usage.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Author](#author)

## Regex Components

### Anchors

Anchors are used to match a specific position in the input string. 
In this regex, we have two anchors:

`^` - The caret anchor denotes the start of the input string.

`$` - The dollar anchor denotes the end of the input string.


The regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` ensures that the email address is matched from the beginning to the end of the string.


### Quantifiers
Quantifiers specify the number of times a character or group can be repeated.

 In this regex we use the following quantifiers:

 `+` Matches one or more occurrences of the preceding element. For example, [a-z0-9_\.-]+ ensures that there is at least one character in the username and domain name parts.

`{2,6}` Matches between 2 and 6 occurrences of the preceding element. In our regex, it ensures that the top-level domain has a length between 2 and 6 characters.


 Snippet of code: 
 ```
 [a-z0-9_\.-]+
 ```


### Grouping Constructs

Grouping constructs are used to group multiple elements together and treat them as a single unit. 
In this regex we use parentheses () to create groups:

([a-z0-9_\.-]+) - This group captures the username part of the email address.
([\da-z\.-]+) - This group captures the domain name part of the email address.
([a-z\.]{2,6}) - This group captures the top-level domain of the email address.


Snippet of code: 
```
([a-z0-9_\.-]+)
```


### Bracket Expressions

Bracket expressions, also known as character classes

In this regex we use bracket expressions to match specific characters:

[a-z0-9_\.-] - Matches any lowercase letter, digit, underscore, period, or hyphen in the username part of the email address.


Snippet of code:
```
`[a-z0-9_\.-]`
```


### Character Classes

Character classes define a set of characters that can be matched at a specific position in the regex. 

- [\da-z\.-] - Matches any digit, lowercase letter, period, or hyphen in the domain name part of the email address.
- [a-z\.] - Matches any lowercase letter or period in the top-level domain part of the email address.


Snippet of code:
```
`[\da-z\.-]`
```


### The OR Operator

The OR operator | allows you to specify multiple alternatives in the regex. In this regex we don't explicitly use the OR operator, but the structure of the regex implies an alternative. The regex matches either a 6-character hexadecimal value or a 3-character hexadecimal value as the top-level domain.


Snippet of code:
```
[a-f0-9]{6}|[a-f0-9]{3}
```


### Flags

Flags are used to modify the behavior of the regex matching. 
In this regex we don't use any flags. However, flags can be appended to the end of the regex (e.g., /regex/g for global matching).


Snippet of code:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```


### Character Escapes

Character escapes allow you to match special characters or characters with special meanings in regular expressions. 
In this regex we don't use explicit character escapes.


```
Snippet of code: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```


## Author

Name: Philip Kubisz
[GitHub Profile](https://github.com/your-profile)
Email: philip.kubisz@gmail.com