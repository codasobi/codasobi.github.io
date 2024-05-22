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
"Hello World!" => "HEllO WOrld!"
```

SOLUTION:
- Define vowels
- Create an blank [] to put char
- Use for loop to find vowel, change to upper case then add into []
- Change [] to string

```
# [expression for item in iterable if condition] 
def swap(str):
    vowel = 'aeiou'
    result = ''.join([char.upper() if char.lower() in vowel else char for char in str])
    return result

#if before for is creating

# for loop
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

#5 [Disemvowel Trolls](https://www.codewars.com/kata/52fba66badcd10859f00097e)

DESCRIPTION:
- Your task is to write a function that takes a string and return a new string with all vowels removed.

```
"This website is for losers LOL!" => "Ths wbst s fr lsrs LL!"
```

SOLUTION:
- Define vowels
- Use a for loop to find char other than vowels and join together

```
# for loop
def disemvowel(string):
    vowels = 'aeiou'
    result = ''
    for char in string:
        if char.lower() not in vowels:
            result += char
    return result

# (expression for item in iterable if condition)
def disemvowel(string):
    vowels = 'aeiou'
    result = ''.join(char for char in string if char.lower() not in vowels)
    return result

#if after for is filtering
```

#6 [Find the Capitals](https://www.codewars.com/kata/53573877d5493b4d6e00050c)

DESCRIPTION:
- Complete the method that takes a sequence of objects with two keys each: country or state, and capital. Keys may be symbols or strings.
- The method should return an array of sentences declaring the state or country and its capital.

```
[{'state': 'Maine', 'capital': 'Augusta'}] => ["The capital of Maine is Augusta"]
[{'country' : 'Spain', 'capital' : 'Madrid'}] => ["The capital of Spain is Madrid"]
[{"state" : 'Maine', 'capital': 'Augusta'}, {'country': 'Spain', "capital" : "Madrid"}] => ["The capital of Maine is Augusta", "The capital of Spain is Madrid"]
```

SOLUTION:
- Create a [] to put in the sentence
- 
```
def capital(capitals): 
    sentences = []
    for item in capitals:
        if 'state' in item:
            sentences.append(f'The capital of {item["state"]} is {item["capital"]}')
        elif 'country' in item:
            sentences.append(f'The capital of {item["country"]} is {item["capital"]}')
    return sentences
```

#7 [Even or Odd](https://www.codewars.com/kata/even-or-odd)

DESCRIPTION:
- Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.

SOLUTION:
- Use % 2 to justify even or odd

```
def even_or_odd(number):
    if number % 2 == 0:
        return 'Even'
    else:
        return 'Odd'
```

#8 [Sum of positive](https://www.codewars.com/kata/5715eaedb436cf5606000381)

DESCRIPTION:
- You get an array of numbers, return the sum of all of the positives ones.

```
Example [1,-4,7,12] => 1 + 7 + 12 = 20
```

SOLUTION:
- Create a sum var
- Use a for loop, if num is positive then add it.

```
def positive_sum(arr):
    sum = 0
    for num in arr:
        if num > 0:
            sum += num
    return sum
```