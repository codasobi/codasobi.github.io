---
title: Codewars practice
description: Codewars is a platform for developers to improve their skills by solving coding kata and learning from peers. These discrete programming exercises train a range of skills in a variety of programming languages, and are completed within an online integrated development environment.
slug: codewar
date: 2024-05-17 07:00:00+0000
categories:
    - codewar
tags:
    - python
---


#1 [Reversed Strings](https://www.codewars.com/kata/5168bb5dfe9a00b126000018)

DESCRIPTION:
Complete the solution so that it reverses the string passed into it.

```
'world'  =>  'dlrow'
'word'   =>  'drow'
```

SOLUTION:
- If input is a string, then reverse it.

```
def solution(string):
    if isinstance(string, str):
        return string[::-1]
```

#2 [Convert string to camel case](https://www.codewars.com/kata/517abf86da9663f1d2000003)

DESCRIPTION:
- Complete the method/function so that it converts dash/underscore delimited words into camel casing. 
- The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case). 
- The next words should be always capitalized.

```
"the-stealth-warrior" => "theStealthWarrior"
"The_Stealth_Warrior" => "TheStealthWarrior"
"The_Stealth-Warrior" => "TheStealthWarrior"
```

SOLUTION:
- Keep first word unchanged, and capitalized the rest of the words
- Need to unify split character '-', '_'
- Split to array, capitalize then join

```
def to_camel_case(text):
    if isinstance(text, str):
        # unify '-' to '_' and split
        words = text.replace('-', '_').split('_')
        camel_words = [words[0]] + [word.capitalize() for word in words[1:]]
        result = ('').join(camel_words)
    return result
```

#3 [Jenny's secret message](https://www.codewars.com/kata/find-the-capitals)

DESCRIPTION:
- Jenny has written a function that returns a greeting for a user. 
- However, she's in love with Johnny, and would like to greet him slightly different. 

```
"Johnny" => "Hello, my love!"
"Mary" => "Hello, Mary"
"Oliver" => "Hello, Oliver"
```

```
def greet(name):
    if name == "Johnny":
        return "Hello, my love!"
    else:
        return "Hello, {name}!".format(name=name)
```

#4 [Changing letters](https://www.codewars.com/kata/5831c204a31721e2ae000294)

DESCRIPTION:
- When provided with a String, capitalize all vowels

```
"Hello World!" "HEllO WOrld!"
```

```
def swap(str):
    vowel = 'aeiou'
    result = []
    for char in str:
        if char.lower() in vowel:
            result.append(char.upper())
        else:
            result.append(char)
    
    return ''.join(result)
```

