
## what regex can do
1. determine whether a string format.  for example, determine an amount string, phone format, email format, or http link format or a valid decimal number. 

2. extraction.  Extraction rule-based string from a text. For example, extract http linked list from html, or extract all the tag names from html, or extract the tag atrributes from html.  

## principle 

convert regex to NFA or DFA using compile principles of lexical analysis, parsing, and  translation. 

## advanced function

1. look ahead or look behind to match the string with some boundary. 
2. group reference ,to reference the group with the same text by using \1, \2, \3 which denotes the first group, the second group and the third group and so on. 
3. Non-greedy match, non greedy match is to match as little as possible, it is ususally used in html matching. 