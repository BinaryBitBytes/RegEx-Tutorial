# Regex 101- Regular Expressions

## Introductory
---
A Regex is known as a Regular expressions, or regex for short, are a series of special characters that define a search pattern. We will navigate a search pattern bases on literal characters that will produce a regex search pattern with a result by deliminating meta characters withing each of the data sets to redact the required results to each of the respected regex components. In this document I will go about describing each of the respected regular expressions in detail and provide a functional example for each regular expression to better help the reader understand how the regular expressions are written and what they are doing.

## Summary
-------------

This document will introduce methods & solutions to provide the reader with the respected solutions that will supplement their understanding of regular expressions. Below in the table of contents I will address each of the topics in detail, provide supporting resources, and best explain and demonstrate these regular expressions with a functioning example. I will include a code snippet of each of the respected regex functions for the reader. In these running examples I will outline the meta characters and explain them such as; __\d for number__ and __. for any character__ as well as __* for 0 or more characters__ and also __combine .* for any character 0 or more__ of which is known as a __'wild card'__.

## Table of Contents
---------------
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components 
---------------

### Anchors

#### *__SOURCES__* :
---------------

>> - __https://www.regular-expressions.info/anchors.html__ : The caret ^ matches the position before the first character in the string and $ matches right after the last character in the string. __*Anchors do not match characters*__, *rather they match positions* of characters __*before, inbetween, or after*__ in a regular expression in a __specific position__ of a string or value. These searches on anchors can only find __zero-length matches__ but they can also be used to create searches for __*complications*__. A user can __trim the leading white space with the regex anchor function of: ^\s+__ and you can __match the trailing whitespace with the regex function of \s+$__. When dealing with a __string that runs multiple lines the regex command of \n indicates a *line break*__. Strings ending with multi line breaks can use regex functions in multi-line mode can leverage the __\Z__ to match before any number of trailing line breaks as well as the end of a string.

#### *__Example__* :
---------------

![anchorRegexExample](https://user-images.githubusercontent.com/94703967/170908620-6a65a7b6-35aa-4b52-9e6f-4d776e00df8b.jpg)


### Quantifiers

#### *__SOURCES__* :
---------------

>> - __http://docs.microsoft.com/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions__ : According to the Microsoft docs on *quantifiers* they are a specification of how many instances of a character, group, or character class that must be present in the input for a match to not be found. Examples of this can be expressed in __Greedy Quantifiers__ and __Lazy Quantifiers__. A few examples of a *greedy quantifier* inclue * (matched zero or more times), + (matches one or more times), ? (matches zero or one time), { n } (matches exactly n amount of times), { n ,} (matches atleast n times), and { n , m } (matches from n to m times). Lazy Quantifiers are referenced simalarly in the examples above the only difference is each of these examples above have a trailing ? mark at the end of the quantifier that make them a Lazy Quantifier.

>> - __https://www.regular-expressions.info/possessive.html__ : 

#### *__Example__* :
---------------

![quantifierRegexExample](https://user-images.githubusercontent.com/94703967/170910938-9c018fd1-3873-4799-bcba-9f06dcdbea7a.png)


### Grouping Constructs

#### *__SOURCES__* :
---------------

>> - __https://docs.microsoft.com/en-us/dotnet/standard/base-types/grouping-constructs-in-regular-expressions__ : A __Grouping Construct__ portrays a subexpression of a regex and captures the substring of the input string. You can use these Grouping Constructs to:

1 Match a subexpression that is repeated in the input string.

2 Apply to a regex in a quantifier to a given subexpression that has multiple language elements.

3 Include grouping constructs in a subexpression in the string that is returned by the regex to us a regex.replace & match.result form of methods.

4 Retreive specific or individual subexpressions from the match.groups property and then process each one seperately from the entirety of a matches text.
These Grouping Constructs come in two types: __Capturing__ & __Noncapturing__.

__Grouping construct__	                        __*Capturing or noncapturing*__
- __Matched subexpressions__                    Capturing
- __Named matched subexpressions__	            Capturing
- __Balancing group definitions__	            Capturing
- __Noncapturing groups__	                    Noncapturing
- __Group options__	                            Noncapturing
- __Zero-width positive lookahead assertions__	Noncapturing
- __Zero-width negative lookahead assertions__	Noncapturing
- __Zero-width positive lookbehind assertions__	Noncapturing
- __Zero-width negative lookbehind assertions__	Noncapturing
- __Atomic groups__	                            Noncapturing

#### *__Example__* :
---------------

![Grouping Construct ](https://user-images.githubusercontent.com/94703967/170913844-958a9892-a488-4e4e-800d-c4ebe60053a7.gif)

### Bracket Expressions

#### *__SOURCES__* :
---------------

>> - __https://www.ibm.com/docs/en/netcoolomnibus/8.1?topic=SSSHTQ_8.1.0/com.ibm.netcool_OMNIbus.doc_8.1.0/omnibus/wip/common/reference/omn_ref_re_bracketexpressions.html__ : According to IBM a *__Bracket Expression__* is used to match a single character or a collating element.The *hyphen* character (-) inbetween charecters within a bracket will __match ranges within the scope of those characters__. Using the __{ }__ *brackets* we can use the brackets with a combination of a number to declare a number of digits in a string to match. Using the carot symbol __^__ we can match any characters except those withing the square brackets, only if the carot is the first character after the opening [ or else it will be treated as a generic charecter and same applys to the hyphen (-). *Other Metacharacters withing square brackets will be treated as normal characters and do not require an escape character.*

__For Example:__
- __[b-g]__ : In this expression we will match characters b,c,d,e,f,g.
- __[xy7-9]__ : In this expression we will match x,y,7,8,9.
- __[yY] [eE] [sS]__ : In this expression we will match any spelling of yes, YES, Yes, YEs, yES and so on of any combination.
- __[^4-7]__ : Matches any characters and numbers except 4,5,6,7.
- __[.fu.]__ : Matches a multi-character collating element, such as fun.
- __[=t=]__ : Matches all collating elements with the same primary sort order as the element, including this element contained as itself.

>> - __https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap09.html__ :

#### *__Example__* :
---------------

![BracketExpressionRegex](https://user-images.githubusercontent.com/94703967/170915057-e10b1186-5b0c-4118-9355-b418c32d1258.gif)

### Character Classes

#### *__SOURCES__* :
---------------

>> - __https://www.regular-expressions.info/charclass.html__ : *Character Classes* are also called a __Character Set__. Character sets are regex's that will match only one out of several characters. There are also __Negated Character Classes__ and these classes match any character that is not in the character class. *Such as __invisible line breaks__*. You can also leverage metacharacters inside character class regex statements.

#### *__Example__* :
---------------

![character classes](https://user-images.githubusercontent.com/94703967/171020790-ff30c4e2-dd90-4362-b91f-515833418f59.jpg)

### The OR Operator

#### *__SOURCES__* : 
---------------

>> - __https://www.ocpsoft.org/tutorials/regular-expressions/or-in-regex/__ : The __OR Operation__ will allow us to prefor a second match using the __Pipe Character ( | )__. You can use grouping and alternations in the OR operation by incorporating a __( ?: )__ in the statement. Here is a lightweight example of the OR operation. Also the __( \\w )__ statement is known as the look-ahead and look-behind statement incorporating __( ?= ) and ( ?! )__ '^I eat (?= excellence | failure)\\w+ for breakfast but I prefer eating ( ?! excellence | dog food)\\w+$.'

#### *__Example__* :
---------------

![OR Operator](https://user-images.githubusercontent.com/94703967/171019568-334f8648-d64a-4eae-9a78-13550544cd2e.gif)


### Flags

#### *__SOURCES__* : 
---------------

>> - __https://javascript.info/regexp-introduction#flags__: According the javascript.info resource there are only 6 flags
1. __i__ : this flag will search for *__Case-Insensitive searches__*; meaning there is not a difference between fun and FUN in a search.
2. __g__ : This flag will search for __ALL MATCHES__. If we didnt use __g__ then only the first match would get returned in our search.
3. __m__ : This flag will cover multiple lines as it is called __Multiline Mode__.
4. __s__ : This flag __enables 'DOTALL' mode that allows the . to match ( \n ); or a __new line character__.
5. __u__ : This flag enables __Unicode Support__. This enables processing of surrogate pairs.
6. __y__ : This flag enables __Sticky Mode__ and searches at the exact position covered in the sticky search position.

#### *__Example__* :
---------------

![flag example with non-atomic lookahead](https://user-images.githubusercontent.com/94703967/171025419-5d303082-0b5a-4072-9f4c-59b920dcfe34.jpg)

### Character Escapes

#### *__SOURCES__* : 
---------------

>> - __https://www.jmp.com/support/help/zh/15.2/index.shtml#page/jmp/escaped-characters-in-regular-expressions.shtml__ : The *backslash* produces a __literal character__ You can use the backslash with common character classes such as __\s__ and __\w__ for __space__ and __word__ characters. Also other escpaed characters are as follows:
- __TwoBackslashes__ : single backslash
- __\A__ :start of a __st__ring
- __\b__ :word bounda__ry. The zero-length string between \w and \W or \W and \w.
- __\B__ :not at a word boundary
- __\cX__ :ASCII control character
- __\d__ :single digit [0-9]
- __\D__ :single character that is NOT a digit [^0-9]
- __\E__ :stop processing escaped characters
- __\l__ :match a single lowercase letter [a-z]
- __\L__ :single character that is not lowercase [^a-z]
- __\Q__ :ignore escaped characters until \E is found
- __\r__ :carriage return
- __\s__ :single whitespace character
- __\S__ :single character that is NOT white space
- __\u__ :single uppercase character [A-Z]
- __\U__ :single character that is not uppercase [^A-Z]
- __\w__ :word character [a-zA-Z0-9_]
- __\W__ :single character that is NOT a word character [^a-zA-Z0-9_]
- __\x00-\xFF__ :hexadecimal character
- __\x{0000}-\x{FFFF}__ :Unicode code point
- __\Z__ :end of a string before the line break

#### *__Example__* :
---------------

![Escape Character](https://user-images.githubusercontent.com/94703967/171028601-b27b91a0-1a05-4399-ad52-d4495fb8f990.png)


## Author

I am BinaryBitBytes, a junior full stack developer learning the craft of coding like a a keyboard warrior. Here Is the link to the summary of Regex101 on my GitHub profile:
https://github.com/BinaryBitBytes/ComputerScience
