# Using Regex Tutorial to match email 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ 

## Summary
Regular expression are used to find patterns of characters within a string. Regular expression are also known as regex, and are frequently used for input validation. In aboved regex example we will be breaking down regular expression to valid email addresses. 
 

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
Anchors do not belong to any matching characters, however anchors assert current position in the string matches a well-determined location. For example ^asserts the beginning of the string and $ asserts the end of the line
### Quantifiers
Quantifier specifiy how many instances of a character, group, or character class must be present in the input for a match to be found . In our example we used + to communicate that there is another sequence to match as a greedy quantifier . In addition to + we are also using {2,6}, this is another greedy qualifier, however this specifies that the input has a minimum of 2 characters and a maximum of 6 character 
### Grouping Constructs
In this example we have 3 group contructs. 

The first capturing group is [a-z0-9_\.-]+ 

The breakdown for the first capturing group is 
    As mentioned, the + matches the previous token between one and unlimited times, as many times as possible, giving back as needed (greedy) 
    
    a-z matches a single character in the range between a  and z(case sensitive), 
    
    0-9 matches a single character in the range between 0 and 9 (case sensitive),

    _ matches the character _ (underscore)
    
    . matches the character . (period)

  - matches the character - (hyphen)

The second capturing group is [\da-z\.-]+ 

The breakdown for the second capturing group is 
    
    Here we see + again . Remember +  matches the previous token between one and unlimited times, as many times as possible, giving back as needed (greedy)

    \d matches a digit (equivalent to [0-9])

    a-z matches a single character in the range between a and z 
    
    \. matches the character . (period)
    
    - matches the character - (hyphen)

The third capturing group is [a-z\.]{2,6} $

The breakdown for the thrid capturing group is 

    {2,6} matches the previous token between 2 and 6 times, as many times as possible, giving back as needed (greedy)

    a-z matches a single character in the range between a and z (case sensitive)

    \. matches the character . (period)

    $ asserts position at the end of the string, or before the line terminator right at the end of the string (if any)


### Bracket Expressions
In this example we have 3 bracket expressions . Each bracket expression contains the information that indentifies with the requirement that needs to be match. The information will be located between opened and closed brackets like this [].
In this example we will look are the 3 bracket expressions. 

Bracket Expression #1: [a-z0-9_\.-] - includes case sensitive characters from a-z, numbers from 0-9 an underscore, periods and hyphens.

Bracket Expression #2: [\da-z\.-] - includes all digits, case sensitive characters from a-z, periods and hyphens

Bracket Expression #3: [a-z\.] - includes case sensitive characters from a-z and periods.

### Character Classes
Character classes or character set  tells regex engine to match only one out of serveral characters by placing the characters you want to match between the square brackets . In this regular expression, /d  matches a digit, /d is used on bracket expression 2 and is equivalent to [0-9].
### The OR Operator (|)
 We do not have an example of the OR operator in email validation, however the OR expression is useful within regex. The OR operator is |. For example /^#?([a-f0-9]{6}|[a-f0-9]{3})$/. The OR operator is seperating the 2 components and it is stating that it match be either [a-f0-9]{6} OR [a-f0-9]{3}.

### Flags
The exception to regex being wrapped in slash characters are flags. Flags are placed at the end of a regex, after the second slash. Flags define additional functionality or limits for the regex. Below are the 3 most common used flags.

g—Global search: the regex should be tested against all possible matches in a string.

i—Case-insensitive search: case should be ignored while attempting a match in a string

m—Multi-line search: a multi-line input string should be treated as multiple lines


### Character Escapes
Backslashes (\) in regex escapes a charcter, otherwise it would be interpreted as \. For example is ({) the open curly bracket is used to begin the quantifier, but adding the (\) before the curly bracket means the regex should look for the open curly bracket instead of the beginning of the quantifier . Note all special characters lose their special significance inside bracket expressions.
## Author

My name is Delmy Elias and I dig regex . 
https://gist.github.com/Dlelias/a8253536bfeaa41bb8001d18eb399430

https://gist.github.com/Dlelias