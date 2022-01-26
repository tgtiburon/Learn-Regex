# Learn-Regex

I am writing the Regular Expression tutorial to help new or seasoned developers who may have questions about what exactly a Regular Expression is, and how they might use it.  This paper will cover what Regex is, and some cases of how it might be used.

## Summary

So what exactly is Regex?  Good question!  I am glad you asked.  Regex is formally known as a Regular Expression, or sometimes even as rational expression.  In a nutshell, Regex is a string of characters the specify a search pattern in text.  In other words, you create the Regex and then compare a string of text to it and it will return TRUE if it matches, or FALSE if it does not.  As a programmer this can be used for many purposes but in particular validating text entry.

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

Anchors do not match any characters at all.  They instead match a specific location before, after, or between characters.  
Key points:     ^ is the start of line anchor
                $ is the end of line anchor

    -^      The Caret denotes the start of a string of characters you want to compare.
            Example: ^a matches -> abc but ^b does NOT match abc.

    -$      The dollar sign is used to match the end of a string.
            Example: c$ matches -> abc but a$ does NOT  match abc

### Quantifiers

A quantifier specifies how often a character or group appears in the string.  I will list the most common quantifiers below.

    -?      The question mark is used to denote either 0 or 1 of the preceding character.
            Example: honor and honour both match ->  honou?r.

    -*      The asterix is used to denote zero or more occurrences of the preceding character.
            Example: a*bc matches -> abc, aabc, or aaabc.

    -+      The plus sign is used to denote one or more occurrences of the preceding characters.
            Example: abc+d matches -> abccd, abccdd, abcddd. NOT: acd  
    
    -{n}    Denotes that the preceding element is matched exactly n times.
            Example: abc{2}def matches -> abcabcdef.  NOT: abcabcabcdef

    -{min,} Denotes the preceding element is matched min or more times.
            Example: ab{3,}cd matches -> abababcd, ababababababcd. NOT abcd

    -{,max} Denotes the preceding element is matched upto max times.
            Example:  ab{,4}cd matches -> abcd, ababababcd. NOT abababababcd.
    
    -{min,max}Denotes the preceding element is matched between min and max times.
            Example: ab{1, 3}cd matches -> abcd, ababcd, abababcd. NOT ababababcd.

    

### OR Operator

    -|      Denotes the choice of alternatives.
            Example: dog|cat matches -> dog or cat. ab|c matches -> ab or ac .

    -[]     Denotes matching any of the characters in the brackets.
            For Example: a[bcd] matches -> ab or ac or ad

### Character Classes

    -[a-Z]  Denotes the choice of lowercase a through uppercase Z.
            Example: [a-Z] matches -> azkrpl
    -.      Period matches any single character.
            Example: /.d/ matches -> ad, ed

    \d      Denotes any  digit.
            Example: \d matches -> 1 or 2
    
    \D      Denotes anything except for a digit.
            Example: \D matches -> A-Z but no digits.

    \w      Denotes any alphanumeric character.
            Example: \w matches ->  a-Z or 0-9.

    \W      Denotes matching everything except for alphanumeric characters
            Example: \W matches -> 400%   only the % would match.

    \s      Denotes matching a single white space character (Space, tab, form feed, line feed)
            Example: \s matches the space in A Dog.
    
    \S      Denotes matching a single character that is NOT a white space.
            Example: \S matches -> A B    matches A 

    \t      Denotes matching a horizontal tab.

    \r      Denotes matching a carriage return.

    \n      Denotes matching a linefeed.

    \v      Denotes matching a vertical tab

    \f      Denotes matching a form-feed.

    \b      Denotes matching a backspace

    \0      Denotes matching a NUL character

    \       Denotes that the next character should be escaped.
            Example: \/  matches -> / character
            Example 2: \* matches -> * character

### Flags

    Regular expression have the ability to use flags to change their default functionality.

    d       Generates indices for substring matching.
    
    g       Allows for global search.

    i       Allows for a search ignoring case.

    m       Allows for a multiline search.

    s       Allows . to match the newline characters.

    u       Enables unicode searches.

    y       Has to be stuck to the beginning of the line.



### Grouping and Capturing

    Grouping is a way to treat multiple characters as a single group.  You make this happen by placing the characters you want grouped together within a set of parenthesis.
    Example: (frog) is a single group containing the 4 letters f r o and g.

    Capturing is when you use 1 or more  groups to match a string.

    Example: Regex for email addresses has many groups for capturing.
    
    (?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9]))\.){3}(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9])|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])

    

### Bracket Expressions

    Brackets mark a set of characters to match.  If you place a ^ inside the brackets it means match anything except for the characters in the brackets.
    Example: [abcd] matches -> "ark"   matches a
    Example 2: [^abcd] -> "ark" matches r
    

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

 Highly effective educator with more than 25 years of experience teaching science and developing meaningful relationships with students. Tenacious problem solver and creative thinker who will help you reach your full-stack web development goals.

If you have any questions about this project feel free to email me at <tg.tiburon@gmail.com>.  

To see the rest of my portfolio, visit [Github](https://github.com/tgtiburon).
![](./images/GitHub-Mark-32px.png)

Below is a graphic displaying my most used languages on github.        

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=tgtiburon)