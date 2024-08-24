# Regex - Matching a Hex Value

The purpose of this gist is to identify the different components that make up a regular expression (Regex) by identifying those parts with an example regex.
Link to the Github Gist: https://gist.github.com/ChrisRome00/bfbd97c0df7ddb2d9d53b94c8a0bbded

## Summary

The following is a regex that is used to match any given Hex Value.

Regex: 
```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors signify that a string begins/or ends with the characters that follow/precede it. In our case we have an anchor '^' in the beginning with a following '#', indicating that what we are looking for is going to begin with the character '#'.
```
/^#...
```
Later in the expression, we have the '$', indicating the closing parameter of what we are specifically matching for, which in our case is this pattern ([a-f0-9]{6}|[a-f0-9]{3}).
```
...([a-f0-9]{6}|[a-f0-9]{3})$/
```

### Quantifiers
Quantifiers can be seen as a further constraint on what we are looking for. Our expression has three of them, the '?' and the following:
```
{6} and {3}
```
This more so acts as a limiter of the length of characters or symbols to what is previously stated before it.
```
[a-f0-9]{6}
```
With a bracket expression, we can now only look for the following strings with a length of 6: aaa000, aa2c44, fff000.
And with the '{3}' it is limited to 3 characters: aaa, 000, fb3.

The '?' acts as making its previously stated character(s) optional. so we can either include or not include the '#' on our search it will still look for the rest of the expression,

### OR Operator
The 'OR' operator is indicated by the '|' pipe symbol. In our expression it is only looking for a pattern that is either matching to its left or right expression.
```
[a-f0-9]{6} | [a-f0-9]{3}
```
So, either we are searching for: aaa000 or aaa, abc123 or ab2, not anything between like something with 5 characters or a letter outside the bounds we are looking for.

### Character Classes
Character classes match any single occurrence if what it is given. In our case we have:
```
...a-f0-9...
```
This means we are looking for any character that lies in between the letter a and f in the alphabet, and the number 0 through 9 to fill that single occurrence.

### Grouping and Capturing
Grouping and capturing are the parentheses used to grab a string of characters. We use it to mark what we exactly are searching for, for us, it is a string with the length of 3 or 6 containing the letters a - f and the numbers 0 -9.
```
([a-f0-9]{6}|[a-f0-9]{3})
```

### Bracket Expressions
Bracket expressions represent a pattern within a set of brackets '[]'. Our regex expression has the following:
```
[a-f0-9]
```
This simply is looking for anything that contains the letters lower-case 'a' through 'f' and any numbers 0 through 10.
Without any constrictors that our regex expression currently has, this 'could' represent: '122das223145dfe', 'abcde12', and so on.

### Greedy and Lazy Match
Our qualifiers {6} and {3} are defined greedy by default. That means our search with this expression will find as many occurrences as possible.

## Author

GitHub: [ChrisRome00](https://github.com/ChrisRome00)
