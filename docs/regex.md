# Regex

A regular expression is an object that describe a pattern of characters, _/pattern/modifiers_.

## Patterns

-   . - Any character except new line
-   \d - Digits (0-9)
-   \D - Non-Digits
-   \w - Word Character (a-z, A-Z, 0-9, \_)
-   \W - Not Word Character
-   \s - Whitespaces (space, tab, new line)
-   \S - Not Whitespaces
-   [] - Matches Characters in Brackets
-   [^] - Matches Characters not in Brackets
-   | - Either Or
-   () - Group
-   \t - Tab
-   \n - Newline
-   \r - Carriage Return

### Anchors ([Link](./anchor.js))

-   \b - Word Boundary
-   B - Not Word Boundary
-   ^ - Beginning of String
-   \$ - End of String
-   \G - Start of Match
-   \A - Start of String
-   \Z - End of String
-   \z - Absolute End of String

### Quantifiers

-   \* - 0 or more
-   \+ - 1 or more
-   ? - 0 or one
-   {3} - Exact Number
-   {3,} - Match 3 or more
-   {,3} - Match 3 or lessa(?=b) Match a in baby but not in bay
    a(?!b) Match a in Stan but not in Stab
    (?<=a)b Match b in crabs but not in cribs
    (?<!a)b Match b in fib but not in fab
-   {3,4} - Range of Numbers (Minimum, Maximum)

## Modifiers

-   g - performs a global match(find all matches rather than stopping after the first match)
-   i - performs case-insensitive matching
-   m - performs multiline matching

## Examples

-   /[a-zA-Z0-9]/ - ranges can be set inside character sets
-   /[^a-z]/ - will match anything that is not a lowercase value from a to z
-   /\d{3}.\d{3}.\d{4}/ - will match anything with exactly (3 digits) + (anything) + (3 digits) + )(anything) + (4 digits)
-   /M(r|s|rs)\.?\s[A-Z]\w\*/ - (will match M) + (r or s or rs) + (0 or One period) + (space) + (letter with captial A - Z) + (0 or more word characters)
-   a(?=b) - Match a in baby but not in bay
-   a(?!b) - Match a in Stan but not in Stab
-   ?<=a)b - Match b in crabs but not in cribs
-   (?<!a)b - Match b in fib but not in fab

## Links

-   https://www.youtube.com/watch?v=sa-TUpSx1JA
-   https://devhints.io/regexp
