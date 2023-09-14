# Regex Explained: Verifying a User's Email

This tutorial aims to demystify regular expressions (regex) by using an example to validate a user's email address. We'll dissect each component of the regex pattern, providing examples of what's accepted and what's not.

## Summary

**Matching an Email:** `^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$`

This regex checks if a user's email input adheres to the standard email format. We'll break down each part of this regex to explain its purpose and what it allows for a valid email.

## Table of Contents

1. Anchors
2. Quantifiers
3. Grouping Constructs
4. Bracket Expressions
5. Character Classes
6. Character Escapes
7. Regex Components

## 1. Anchors

Regular expressions use two anchors: `^` and `$`. 

- `^` signifies the start of the expression, stating that what follows should match from the beginning.
- `$` is found at the end of the regex, marking the end of the string to be matched, essentially enclosing the regex defined by `^`.

## 2. Quantifiers

Quantifiers set limits for the string that the regex is matching with. Common quantifiers include:

- `*`: Matches the pattern zero or more times.
- `+`: Matches the pattern one or more times.
- `?`: Matches the pattern zero or one time.
- `{}`: Curly brackets provide different ways to set limits.
  - `{n}`: Matches the pattern exactly `n` times.
  - `{n,}`: Matches the pattern at least `n` times.
  - `{n,x}`: Matches the pattern from a minimum of `n` times to a maximum of `x` times.

In our example, `{2,6}` allows the string to contain 2 to 6 characters, as seen in `.([a-z.]{2,6})`.

- Correct Ending: `.com` (valid as it contains lowercase letters and falls within the 2-6 character limit).
- Invalid Ending: `.c0mMercial` (invalid due to including numbers, uppercase letters, and exceeding 6 characters).

## 3. Grouping Constructs

Group constructs divide the string into sections. In our email example, we use three grouping constructs: `([a-z0-9_.-]+)`, `([\da-z.-]+)`, and `([a-z.]{2,6})`. Each has its rules, ensuring the regex outlines a valid email.

## 4. Bracket Expressions

Bracket expressions represent character ranges that need to be matched. We have three instances:

1. `[a-z0-9_.-]`: Accepts lowercase letters from `a-z`, numbers from `0-9`, `_`, `.`, and `-`.
   - Valid: "av_dyt.8b-1"
   - Invalid: "AC%$#@()"

2. `[\da-z.-]`: Accepts any digit (`\d` represents 0-9), lowercase letters `a-z`, `.`, and `-`.
   - Valid: "6xa.ar-"
   - Invalid: "$ARF(#)"

3. `[a-z.]`: Accepts lowercase letters from `a-z` and `.`.
   - Valid: ".net"
   - Invalid: "%COM)@"

## 5. Character Classes

Character classes define sets of characters. Common character classes include:

- `.`: Matches any character except the newline character (`\n`).
- `\d`: Matches any Arabic numeral digit (equivalent to `[0-9]`).
- `\w`: Matches any alphanumeric character from the basic Latin alphabet, including `_` (equivalent to `[A-Za-z0-9]`).
- `\s`: Matches a single whitespace character, including tabs and line breaks.

## 6. Character Escapes

Character escapes are used to specify whether a character should be treated literally or not. The `\` key escapes characters that would otherwise have special meanings in regex. In our example, `\.` allows `.` to be treated as a literal period.

## 7. Regex Components

- `^`: Start of the string.
- `([a-z0-9_\.-]+)`: Matches the username part of the email.
- `@`: Matches the "@" symbol.
- `([\da-z\.-]+)`: Matches the domain name (e.g., "gmail").
- `\.`: Matches a literal period.
- `([a-z\.]{2,6})`: Matches the top-level domain (e.g., "com").
- `$`: End of the string.

**Author:** https://github.com/Josiahr4321

This tutorial breaks down the regular expression into its fundamental components, making it easier for readers to understand and apply regex for email validation and beyond.
