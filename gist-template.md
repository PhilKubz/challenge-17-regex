# Regex Tutorial: Matching an Email


## Summary

Regular expressions, often abbreiavted to regex, are tools for pattern matching. Regular expressions are used in programming languages, text editors, and CLI tools to perform tasks like data validation, search and replace text, as well as parsing. One common use is validating email addresses!

We are going to look into validating email addresses with the help of a regex expression.

In this tutorial, we are going to take a look at the regular expression:

 `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` 

and demonstrate how it can be used to match email addresses. When breaking down the components of the regex expression, we will explain the functionality as well as including examples of code to demonstrate the usage.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Author](#author)
- [Examples](#examples)

## Regex Components


## Anchors

Anchors are used to match a specific position in the input string. 
In this regex, we have two anchors: `^` and `$`. These are placed in the expression to insure that the email is matched from the beginning til the end of the string.

`^` - The caret anchor denotes the start of the input string

`$` - The dollar anchor denotes the end of the input string


The regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` is what we use to ensure that the email address is matched from beginning to end of the strong. And in this entire expression, we see that the first/last component are the anchors.



## Quantifiers

Quantifiers specify the number of times that a character or group can be repeated.

 In this regex we use the following quantifiers:

 `+` Matches one or more occurrences of the preceding element. For example, `[a-z0-9_\.-]+` makes sure that there is at least one character in the username and domain parts

`{2,6}` Matches between 2 and 6 occurrences of the preceding element. In our regex, it ensures that the top-level domain has a length between 2 and 6 characters 
(This is the part that comes after the "." at the end of the email. 
Examples of TLD are `.com` `.org` `.gov` `.uk`, these are examples of 2 and 3 character TLD -- between 2 and 6 characters are allowed in this regex expression)


 Snippet of code: 
 ```
 [a-z0-9_\.-]+
 ```



## Grouping Constructs

Grouping constructs are used to group multiple elements together and treat them as a single unit. 
In this regex we use parentheses () to create groups:

Snippet of Code
```
([a-z0-9_\.-]+)
```

`([a-z0-9_.-]+)` - This group captures the username part of the email address
+ The character class `[a-z0-9_\.-]` matches any lowercase letter, digit, underscore, period, or hyphen


Snippet of code: 
```
([\da-z\.-]+)
```

`([\da-z\.-]+)` - This group captures the domain name part of the email address
+ The character class `[\da-z\.-]` matches any digit, lowercase letter, period, or hyphen


`([a-z\.]{2,6})` - This group captures the top-level domain of the email address
+ The character class `[a-z\.]` matches any lowercase letter or period



## Bracket Expressions

Bracket expressions are used to define the valid characters that can appear in the username part of the email address. By defining and enforcing the specific characters of the usernam portion of the email, it helps determine the validity of the email.

In this regex we use bracket expressions to match specific characters:

`[a-z0-9_\.-]` - Matches any lowercase letter, digit, underscore, period, or hyphen in the username part of the email address.

More specifically:
+ a-z: Matches any lowercase letter from 'a' to 'z'
+ 0-9: Matches any digit from '0' to '9'
+ _: Matches an underscore character
+ \.: Matches a period character (dot) using a backslash to escape its special meaning in regular expressions
+ -: Matches a hyphen character


Snippet of code:
```
`[a-z0-9_\.-]`
```



## Character Classes

Character classes define a set of characters that can be matched at a specific position in the regex. 

`[\da-z\.-]` - Matches any digit, lowercase letter, period, or hyphen in the domain name part of the email address.

+ \d: Matches any digit
+ a-z: Matches any lowercase letter from 'a' to 'z'
+ \.: Matches a period character (dot)
+ -: Matches a hyphen character


`[a-z\.]` - Matches any lowercase letter or period in the top-level domain part of the email address.

+ a-z: Matches any lowercase letter from 'a' to 'z'
+ \.: Matches a period character (dot)

The inclusion of this in our regex expression helps ensure the domain name and top-level domain parts of the email address contain only valid characters to match a valid email address.

Snippet of code:
```
`[\da-z\.-]`
```


## Flags

Flags are used to modify the behavior of the regex matching. 
In this regex we don't use any flags. However, flags can be appended to the end of the regex (e.g., /regex/g for global matching). The absence of any flags means that the regex only matches the first occurrence of the pattern in the input string and performs a case-sensitive matching.


Snippet of code:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
## Examples

In this section I will provide some example email addresses that are either valid or invalid according to our regex expression.

Valid Email Addresses
+ `first.last@example.com`
+ `info@example.org`


Invalid Email Addresses
+ `first.last@example`
+ `first last@example.com`

While this may not cover all possible edgecases with our regex expression, it will provide a very simple tool for validation of email addresses for an application!

## Author

Name: Philip Kubisz
[GitHub Profile](https://github.com/PhilKubz?tab=repositories)
Email: philip.kubisz@gmail.com