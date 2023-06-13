# Regex Tutorial: Matching an Email


## Summary

In this tutorial, we are going to take a look at the regular expression:

 `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` 
 
and demonstrate how it can be used to match email addresses. When breaking down the components of the regex expression, we will explain the functionality as well as including examples of code to demonstrate the usage.


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


## Anchors

Anchors are used to match a specific position in the input string. 
In this regex, we have two anchors:

`^` - The caret anchor denotes the start of the input string.

`$` - The dollar anchor denotes the end of the input string.


The regex `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` is what we use to ensure that the email address is matched from beginning to end of the strong.



## Quantifiers
Quantifiers specify the number of times that a character or group can be repeated.

 In this regex we use the following quantifiers:

 `+` Matches one or more occurrences of the preceding element. For example, [a-z0-9_\.-]+ makes sure that there is at least one character in the username and domain parts.

`{2,6}` Matches between 2 and 6 occurrences of the preceding element. In our regex, it ensures that the top-level domain has a length between 2 and 6 characters 
(This is the part that comes after the "." at the end of the email. 
Examples of TLD are `.com` `.org` `.gov` `.net`, all of these are examples of 3 character TLD)


 Snippet of code: 
 ```
 [a-z0-9_\.-]+
 ```



## Grouping Constructs

Grouping constructs are used to group multiple elements together and treat them as a single unit. 
In this regex we use parentheses () to create groups:

([a-z0-9_\.-]+) - This group captures the username part of the email address.
([\da-z\.-]+) - This group captures the domain name part of the email address.
([a-z\.]{2,6}) - This group captures the top-level domain of the email address.


Snippet of code: 
```
([a-z0-9_\.-]+)
```



## Bracket Expressions

Bracket expressions are used to define the valid characters that can appear in the username part of the email address. By defining and enforcing the specific characters of the usernam portion of the email, it helps determine the validity of the email.

In this regex we use bracket expressions to match specific characters:

[a-z0-9_\.-] - Matches any lowercase letter, digit, underscore, period, or hyphen in the username part of the email address.

More specifically:
+ a-z: Matches any lowercase letter from 'a' to 'z'.
+ 0-9: Matches any digit from '0' to '9'.
+ _: Matches an underscore character.
+ \.: Matches a period character (dot) using a backslash to escape its special meaning in regular expressions.
+ -: Matches a hyphen character.


Snippet of code:
```
`[a-z0-9_\.-]`
```



## Character Classes

Character classes define a set of characters that can be matched at a specific position in the regex. 

[\da-z\.-] - Matches any digit, lowercase letter, period, or hyphen in the domain name part of the email address.

+ \d: Matches any digit.
+ a-z: Matches any lowercase letter from 'a' to 'z'.
+ \.: Matches a period character (dot).
+ -: Matches a hyphen character.


[a-z\.] - Matches any lowercase letter or period in the top-level domain part of the email address.

+ a-z: Matches any lowercase letter from 'a' to 'z'.
+ \.: Matches a period character (dot).

The inclusion of this in our regex expression helps ensure the domain name and top-level domain parts of the email address contain only valid characters to match a valid email address.

Snippet of code:
```
`[\da-z\.-]`
```



## The OR Operator

The OR operator | allows you to specify multiple alternatives in the regex. In this regex we don't explicitly use the OR operator, but the structure of the regex implies an alternative. The regex matches either a 6-character hexadecimal value or a 3-character hexadecimal value as the top-level domain.


Snippet of code:
```
[a-f0-9]{6}|[a-f0-9]{3}
```



## Flags

Flags are used to modify the behavior of the regex matching. 
In this regex we don't use any flags. However, flags can be appended to the end of the regex (e.g., /regex/g for global matching). The absence of any flags means that the regex only matches the first occurrence of the pattern in the input string and performs a case-sensitive matching.


Snippet of code:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```



## Character Escapes

Character escapes allow you to match special characters or characters with special meanings in regular expressions. 
In this regex we don't use explicit character escapes as each character in the regex has a literal meaning.



Snippet of code:
```
 /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```



## Author

Name: Philip Kubisz
[GitHub Profile](https://github.com/PhilKubz?tab=repositories)
Email: philip.kubisz@gmail.com