# Email Validator Regular Expression

Regular expressions also known as regex are a series of special characters that define a search pattern and validate specific strings.

## Summary

The regular expression /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ is used to validate email addresses. It checks whether a string follows a specific pattern to form a valid email address.

## Table of Contents

- [Email Validator Regular Expression](#email-validator-regular-expression)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [Author](#author)

## Regex Components

1. ^: The start anchor asserts that the match must start at the beginning of the text.

2. ([a-z0-9_\.-]+): The first capturing group that matches the local part of the email address before the "@" symbol. This matches any lowercase letter (a-z), digit (0-9), underscore (_), period (.), or hyphen (-). The plus symbol means that the next character class should occur one or more times, allowing multiple characters in the local part of the email address.

3. ([\da-z\.-]+): The second capturing group, matches the domain name after the "@" symbol. Matches any lowercase letter (a-z), digit (0-9), period (.), or hyphen (-). The plus symbol means that the preceding character class should occur one or more times, allowing multiple characters in the domain name. \. matches the period (dot) in the domain name. The period is a special character in regex, so it needs to be escaped with a backslash to match a literal period.

4. ([a-z\.]{2,6}): This is the third capturing group, which matches the top-level domain (TLD) part of the email address. Matches any lowercase letter (a-z) or a period (dot). {2,6} is a quantifier that specifies that the preceding character class should occur between 2 to 6 times, allowing TLDs with lengths like ".com", ".org", ".info", etc.

5. $: The end anchor. It asserts that the match must end at the end of the text.

### Anchors

- ^ (caret symbol): This is the start anchor thats asserts that the match must start at the beginning of the text. In this case, it means that the email address must begin with the pattern specified in the regular expression.

- $ (dollar sign): This is the end anchor that asserts that the match must end at the end of the text. This means that the email address must end with the pattern specified in the regular expression.

### Quantifiers

  - + (Plus Symbol): The plus symbol is a quantifier that matches one or more occurrences of the preceding element. In this regex, it is used in two places:

([a-z0-9_\.-]+):  matches one or more occurrences of lowercase letters (a-z), digits (0-9), underscores (_), periods (.), or hyphens (-) in the local part of the email address. This allows the local part to have multiple characters.

([\da-z\.-]+):  matches one or more occurrences of lowercase letters (a-z), digits (0-9), periods (.), or hyphens (-) in the domain name part of the email address. This allows the domain name to have multiple characters.

([a-z\.]{2,6}): It matches a sequence of lowercase letters (a-z) or periods (.) in the top-level domain (TLD) part of the email address. The quantifier {2,6} means that the TLD can have a minimum of 2 characters and a maximum of 6 characters. This allows the TLD to be, for example, ".com", ".org", ".info", etc.

### OR Operator

- Or operator is done by [a-z0-9_\.-], allows any character from this set to be matched. and ([\da-z\.-]+), allows multiple characters from this set to be matched in sequence.

### Character Classes

- [a-z0-9_\.-]:
a through z (all lowercase letters)
0 through 9 (all digits)
_ (underscore)
. (period)
(hyphen)

- [\da-z\.-]:
a through z (all lowercase letters)
0 through 9 (all digits)
. (period)
(hyphen)

- [a-z\.]:
a through z (all lowercase letters)
. (period)

### Flags

- No flags applicable.

### Grouping and Capturing

- Group 1 ([a-z0-9_\.-]+), matches one or more lowercase letters between a-z, numbers between 0-9, underscores, periods, and hyphens. The expression is then followed by an @ sign.

- Group 2 ([\da-z\.-]+) - the domain name must be matched which can use one or more digits, letters between a-z, periods, and hyphens. The domain name is then followed by a period \..

- Group 3 ([a-z\.]{2,6}) - matches the top level domain. This section looks for any group of letters or dots that are 2-5 characters long. This can also account for region-specific top level domains.

### Bracket Expressions

- [a-z0-9_\.-], matches characters in the local part of the email address before the "@" symbol.
- ([\da-z\.-]+), matches characters in the domain name part of the email address after the "@" symbol
- [a-z\.], matches any lowercase letter (a-z) or a period (.) in the third capturing group

### Greedy and Lazy Match

- Greed and lazy match not applicable.

### Boundaries

- The anchor and dollar sign ensures there are no other characters before or after the email address.

### Back-references

- No back referneces applicable.

### Look-ahead and Look-behind

- No look-ahead or look-behind applicable.

## Author

Steve Kim, Github: <https://github.com/won-shy>.
