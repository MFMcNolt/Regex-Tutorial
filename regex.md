# Regex Tutorial: Matching a Hex Value

Regular expressions, or regex for short, are a series of special characters that define a search pattern. 

Take the example of a regular expression, which we will call "Hex Value."

```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```

Regular expressions can feel like their own language at times, but in fact they are universal and can be used within all programming languages. Let's break down the preceding “Hex Value” regex in order to explore regex components in general.

## Summary
Hex value plays a crucial role in web development for defining colors in a hexadecimal format. It accommodates both 3-digit and 6-digit hex values, with or without the leading hash (#) symbol. In this tutorial, we will explore a regular expression designed to validate Hex Value. Let's break down the regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ for matching a hex value:

- /: Delimiters for the start of the regular expression.
- ^: Anchors the match at the beginning of the string.
- #?: Matches zero or one occurrence of the hash (#) symbol.
- ([a-f0-9]{6}|[a-f0-9]{3}): A group that matches either six or three hexadecimal characters:
    - [a-f0-9]: Matches any character in the range a-f or 0-9.
    - {6}: Specifies that there should be six consecutive characters (for the six-digit case).
    - |: Alternation, allowing either the six-digit or three-digit pattern.
    - {3}: Specifies that there should be three consecutive characters (for the three-digit case).
- $: Anchors the match at the end of the string.

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

In regular expressions, anchors are special characters that assert a specific position in the input string. They don't match any characters themselves but define the position at which the pattern inside the regex should match. There are two main types of anchors:

- ^(Caret): Anchors the regex at the beginning of the string. It asserts that the following pattern should match at the very start of the input.
- $(Dollar Sign): Anchors the regex at the end of the string. It asserts that the preceding pattern should match at the very end of the input.

### Quantifiers

Quantifiers in regular expressions are symbols that specify the number of occurrences of a character or a group of characters. They allow you to define how many times a particular element should be repeated in order for a match to occur. Now, let's point out the quantifiers in the hex value regex:

- ? (Question Mark): This quantifier is used in #?, allowing for zero or one occurrence of the hash symbol (#). It means the hash symbol is optional.
- {6}: This quantifier is used in [a-f0-9]{6}, specifying that there should be exactly six consecutive characters matching the range of lowercase letters 'a' to 'f' or digits '0' to '9'. This accounts for the 6-digit hex color value.
- {3}: This quantifier is used in [a-f0-9]{3}, specifying that there should be exactly three consecutive characters matching the same range. This accounts for the 3-digit hex color value.

### Grouping Constructs
Grouping constructs in regular expressions allow you to treat multiple characters or sub-patterns as a single unit. They are created using parentheses () and serve several purposes. Now, let's point out the grouping constructs in the hex value regex, specifically, ([a-f0-9]{6}|[a-f0-9]{3}) that matches either six or three hexadecimal characters.

- [a-f0-9] (Character Class Inside the Group): This character class is part of the group and matches any character in the range a-f or 0-9.
- {6} (Quantifier Inside the Group): This quantifier specifies that there should be exactly six consecutive characters matching the character class, for the 6-digit hex color value.
- | (Alternation Inside the Group): This alternation allows either the six-digit pattern or the three-digit pattern to be matched.
- {3} (Quantifier Inside the Group): This quantifier specifies that there should be exactly three consecutive characters matching the character class, for the 3-digit hex color value.

### Bracket Expressions
Bracket expressions, also known as character classes, are a way to specify a set of characters that you want to match in a single position of the input string. They are defined by enclosing characters inside square brackets []. In a bracket expression, a hyphen - denotes a range of characters, and the expression matches any single character within that range. For hex value:

- [a-f0-9] (Bracket Expression): This bracket expression is part of the grouping construct and matches any character that is either a lowercase letter from 'a' to 'f' or a digit from 0 to 9.

### Character Classes
As mentioned, Character classes in regular expressions, often denoted within square brackets [], allow you to define a set of characters from which you want to match a single character. They are a concise way to express a group of characters that you want to include in a specific position within the pattern. In the context of the hex value regex:

- [a-f0-9] (Character Class): This character class specifies a range of valid characters. It matches any valid hexadecimal character, whether it's a digit or a lowercase letter from 'a' to 'f'.

### The OR Operator
The | symbolizes the OR operator, allowing the regex to match either a 6-digit or a 3-digit hex value. It allows you to specify alternatives within a pattern, indicating that either the expression on the left or the one on the right can match. This is particularly useful when you want to allow multiple patterns to be considered as valid matches. 

### Flags
In regular expressions, flags are optional parameters that can be added to the end of a regex pattern to modify its behavior. Flags are used to control aspects such as case sensitivity, multiline matching, and global matching. In many regex implementations, flags are represented by single-letter characters, and they follow the closing delimiter of the regex. One common flag is the case-insensitive flag, denoted by i. The case-insensitive flag allows the regex to match characters regardless of their case, making the matching process insensitive to whether letters are uppercase or lowercase.

### Character Escapes
In regular expressions, character escapes are used to match special characters or to give special meaning to certain characters. They are typically represented by a backslash \ followed by a specific character or sequence. Character escapes allow you to match characters that have a special meaning in regex, such as metacharracters, or to represent characters that are difficult to type directly in a regex pattern. The forward slash / at the beginning and the end are used to help indicate where the string begins and ends.


This tutorial was written by Marion Ferguson McMNulty. Connect with @MFMcNolt on GitHub.