# Regex Tutorial

A regular expression, or Regex, is a string that defines a search pattern in an algorithm or some software code. The most common uses for regex would be to validate that a user input a valid email where required, or to search for a specific string of text within a larger body of text. The easiest way to see it in action may be to open up a web page in your browser, and hit `CTRL` + `F` to "find" a word or phrase.

## Summary

The regex used for this tutorial is one used to search a given text for an email and is as follows:  

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  

This regex matches an email search and can be used to find all emails within a body of text or to verify an input.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

### Anchors
When examining a regex, the starting starting points for the expression would be the anchors. In our example, they are identified as `^` and `$`. They indicate the beginning and end of the expression respectively.  Anchors do not match characters in the expression, but instead match `positions`.  

Let's take a look at what is between the Anchors: `([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`. Since these contents are between the anchors, then our search much match characters defined by these parameters. We'll break this down into individual components below and make more sense of it.  

### Quantifiers

Quantifiers are used in a regex to specify how many instances of a character, group, or class MUST be present in the input in order for it to match. Let's examine what they are doing in their respective use cases.

The `+` quantifier in our regex indicates that there will be one or more of that type of character or group of characters in the match. 

The `{}` quantifier can be used a couple of ways. In our case, it is written as `{2,6}` which means that the preceding character search must match between `2` and `6` times. 

To summarize, the holistic use cases for `{}` can be written as follows:
```
{ n } = Match exactly n times.  
{ n, } = Match at least n times.  
{ n, m } = Match between n and m times.
```

### OR Operator
OR Operators, also known as "bracket expressions" are indicated by square brackets in regex: `[]`. Let's examine how they are used in our email search by breaking them down into segments.  

`[a-z0-9_\.-]` | This group is saying that any letter from a-z, OR any integer from 0-9, OR a `.` OR a `-` in this section would return a match.  
`[\da-z\.-]` | This group is saying that any DIGIT, OR any letter from a-z, OR a `.`, OR a `-` would return a match for this section.  
`[a-z\.]` | This group is saying that any letter from a-z, OR a `.` would return a match for this section.

You can see that the `[]` group up possible characters to indicate that the section can contain any of the different types between the brackets.

### Character Classes
A character class defines a set of characters, any one of which can occur in an input string for a match to succeed. In our regex we have a couple of these.

`\d` is a character class that looks for any digit 0-9.
`\da-z\` indicates we are looking specifically for a character that is either a digit or letter from a-z. 

### Flags
Flags are indicated by forward slashes `/` are used to begin and end the expression. Expressions leverage the forward slash flags to set boundaries on a search pattern. In our case, the flags are using standard functionality to begin and end the expression. Other ways to utilize flags would be to make the search case insensitive, or look for all matches vs only the first match, or perhaps to find text within a specific position of the text.

### Grouping and Capturing
Grouping and capturing are accomplished in regex using parentheses. We can see that our email search is broken into 3 groups using `()`.

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`  
`([a-z0-9_\.-]+)` `([\da-z\.-]+)` `([a-z\.]{2,6})`  

The grouping of this breaks up the search into segments that match an email. For example, we can designate each section by an X here: `X @ X . X`

### Bracket Expressions
Bracket expressions are used to define the matchable characters within a capture group. In our case, the groups are indicated by the parentheses so each `()` is always inwardly followed by `[]`. However, we could use bracket expressions to separate types of characters within a group. For example, rather than `([])` we could have a regex with `([][])`.

### Greedy and Lazy Match
Greedy and Lazy matches refer to the restrictiveness of a particular character type or group in the regex. In our email regex, we only have one of these as indicated by the `+`. In our use case, the `+` is "greedy" because it will match as many times as possible within the group. If our regex contained `A+`, then it would match with "A", "AA" or for as many "A"s that are in that segment.

A Lazy match would operate opposite of a Greedy match in that it would try to limit the search to as few instances as possible. Lazy matches are indicated by a `?`. 

## Author

My name is Julian and I am a new web developer. As such, I am open to any/all feedback or questions you may have. Please contact me at my github if you'd like to reach out.  

Github: [https://github.com/svnday/](https://github.com/svnday/)
