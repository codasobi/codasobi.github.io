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
# maketrans
def disemvowel(string):
    vowel = 'aeiou'
    table = str.maketrans('', '', vowel)
    return string.lower().translate(table)


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

#9 [You're a square!](https://www.codewars.com/kata/54c27a33fb7da0db0100040e)

DESCRIPTION:
- Given an integral number, determine if it's a square number:

```
-1  =>  false
 0  =>  true
 3  =>  false
 4  =>  true
25  =>  true
26  =>  false
```

SOLUTION:
- Square number is >= 0
- Use math.sqrt to check root
- If result is int, then it is a square number

```
import math
def is_square(n):
    if n >= 0:
        return math.sqrt(n).is_integer()
    else:
        return False
```

#10 [Keep Hydrated](https://www.codewars.com/kata/582cb0224e56e068d800003c)

DESCRIPTION:
- Nathan knows it is important to stay hydrated, he drinks 0.5 litres of water per hour of cycling.
- You get given the time in hours and you need to return the number of litres Nathan will drink, rounded to the smallest value.

```
time(hr) = 3 => litres = 1
time(hr) = 6.7 => litres = 3
time(hr) = 11.8 => litres = 5
```

SOLUTION:
- 3 * 0.5 = 1.5 => 1
- 6.7 * 0.5 = 3.35 => 3
- 11.8 * 0.5 = 5.9 => 5
- Use math.floor()

```
import math
def litres(time):
    # 1 hour need 0.5 liter
    return math.floor(time * 0.5)
```

#11 [Calculate Average](https://www.codewars.com/kata/calculate-average)

DESCRIPTION:
- Write a function which calculates the average of the numbers in a given list.
- Empty arrays should return 0.

SOLUTION:
- empty array, lens(number) will be 0 (ZeroDivisionError: division by zero)
- use sum() and lens()

```
def find_average(numbers):
    if len(numbers) == 0:
        return 0
    else:
        return sum(numbers) / len(numbers)
```

#12 [Abbreviate a Two Word Name](https://www.codewars.com/kata/57eadb7ecd143f4c9c0000a3)

DESCRIPTION:
- Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.
- The output should be two capital letters with a dot separating them.

```
Sam Harris => S.H
patrick feeney => P.F
```

SOLUTION:
- split name to []
- upper first char and join with '.'

```
def abbrev_name(name):
    parts = name.split(' ')
    abbr = '.'.join(part[0].upper() for part in parts)
    return abbr
```

#13 [Categorize New Member](https://www.codewars.com/kata/categorize-new-member/train/python)
- To be a senior, a member must be at least 55 years old and have a handicap greater than 7. 
- In this croquet club, handicaps range from -2 to +26; the better the player the lower the handicap.
- Input will consist of a list of pairs. 
- Each pair contains information for a single potential member. 
- Information consists of an integer for the person's "age" and an integer for the person's "handicap".
- Output will consist of a list of string values (in Haskell and C: Open or Senior) stating whether the respective member is to be placed in the senior or open category.

```
input =  [[18, 20], [45, 2], [61, 12], [37, 6], [21, 21], [78, 9]]
output = ["Open", "Open", "Senior", "Open", "Open", "Senior"]
```

SOLUTION:
- Create a []
- Use a for loop, if match senior's condition then append 'Senior'
- Other append 'Open'

```
def open_or_senior(data):
    result = []
    for item in data:
        if item[0] >= 55 and item[1] > 7:
            result.append('Senior')
        else:
            result.append('Open')
    return result
```

#14 [Find the smallest integer in the array](https://www.codewars.com/kata/find-the-smallest-integer-in-the-array)

DESCRIPTION:
- Given an array of integers your solution should find the smallest integer.

```
Given [34, 15, 88, 2] your solution will return 2
Given [34, -345, -1, 100] your solution will return -345
```

SOLUTION:
- Use min() to find the int 

```
def find_smallest_int(arr):
    return min(arr)
```

#15 [Counting Duplicates](https://www.codewars.com/kata/counting-duplicates)

DESCRIPTION:
- Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. 
- The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.

```
"abcde" => 0 # no characters repeats more than once
"aabbcde" => 2 # 'a' and 'b'
"aabBcde" => 2 # 'a' occurs twice and 'b' twice (`b` and `B`)
"indivisibility" => 1 # 'i' occurs six times
"Indivisibilities" => 2 # 'i' occurs seven times and 's' occurs twice
"aA11" => 2 # 'a' and '1'
"ABBA" => 2 # 'A' and 'B' each occur twice
```

SOLUTION:
- Create a {} to count chars
- Count if key's value > 1

```
def duplicate_count(text):
    counter = {}
    for char in text.lower():
        if char in counter:
            counter[char] += 1
        else:
            counter[char] = 1
    
    count = 0
    for item in counter.values():
        if item > 1:
            count += 1
#     count = sum(1 for item in counter.values() if item > 1 )
    return count
```

#16 Counting Sheep (https://www.codewars.com/kata/54edbc7200b811e956000556)

DESCRIPTION:
- Consider an array/list of sheep where some sheep may be missing from their place. 
- We need a function that counts the number of sheep present in the array (true means present).
- Hint: Don't forget to check for bad values like null/undefined

```
[True,  True,  True,  False,
  True,  True,  True,  True ,
  True,  False, True,  False,
  True,  False, False, True ,
  True,  True,  True,  True ,
  False, False, True,  True] => 17
```

SOLUTION:
- Use a for loop, if True, count + 1

```
def count_sheeps(sheep):
    count = 0
    for status in sheep:
        if status:
            count += 1
        else:
            continue
#     count = sum(1 for status in sheep if status)
    return count
```

#17 [Unique In Order](https://www.codewars.com/kata/unique-in-order)

DESCRIPTION:
- Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.

```
unique_in_order('AAAABBBCCDAABBB') => ['A', 'B', 'C', 'D', 'A', 'B']
unique_in_order('ABBCcAD')         => ['A', 'B', 'C', 'c', 'A', 'D']
unique_in_order([1, 2, 2, 3, 3])   => [1, 2, 3]
unique_in_order((1, 2, 2, 3, 3))   => [1, 2, 3]
```

SOLUTION:
- Use groupby to group, and return the keys

```
from itertools import groupby
def unique_in_order(sequence):
    return [key for key, group in groupby(sequence)]
```

#18 [Find the Difference in Age](https://www.codewars.com/kata/5720a1cb65a504fdff0003e2)

DESCRIPTION:
- At the annual family gathering, the family likes to find the oldest living family member’s age and the youngest family member’s age and calculate the difference between them.
- You will be given an array of all the family members' ages, in any order. 
- The ages will be given in whole numbers, so a baby of 5 months, will have an ascribed ‘age’ of 0. 
- Return a new array (a tuple in Python) with [youngest age, oldest age, difference between the youngest and oldest age].

```
[16, 22, 31, 44, 3, 38, 27, 41, 88] => (3, 88, 85))
```

SOLUTION:
- Use max() and min() to calculate and return a tuple

```
def difference_in_ages(ages):
    return (min(ages), max(ages), max(ages) - min(ages))
```

#19 [Array diff](https://www.codewars.com/kata/array-dot-diff)

DESCRIPTION:
- Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.
- It should remove all values from list a, which are present in list b keeping their order.

```
array_diff([1,2],[1]) == [2]
array_diff([1,2,2,2,3],[2]) == [1,3]
```

SOLUTION:
```
def array_diff(a, b):
    return [item for item in a if item not in b]
```

#20 [Century From Year](https://www.codewars.com/kata/5a3fe3dde1ce0e8ed6000097/)

DESCRIPTION:
- Given a year, return the century it is in.

```
1705 --> 18
1900 --> 19
1601 --> 17
2000 --> 20
2742 --> 28
```

SOLUTION:
- if the num could not be devided by 100, then will round up

```
import math
def century(year):
    return math.ceil(year / 100)
```

#21 [Isograms](https://www.codewars.com/kata/54ba84be607a92aa900000f1/train/python)

DESCRIPTION:
- An isogram is a word that has no repeating letters, consecutive or non-consecutive. 
- Implement a function that determines whether a string that contains only letters is an isogram. 
- Assume the empty string is an isogram. 
- Ignore letter case.

```
"Dermatoglyphics" => true
"aba" => false
"moOse" => false (ignore letter case)
```

SOLUTION:
- Change all char to lower case.
- Compare string length with set(string) length

```
def is_isogram(string):
    string = string.lower()
    if len(string) == len(set(string)):
        return True
    else:
        return False
```

#22 [Two to One](https://www.codewars.com/kata/5656b6906de340bd1b0000ac/train/python)

DESCRIPTION:
- Take 2 strings s1 and s2 including only letters from a to z. 
- Return a new sorted string, the longest possible, containing distinct letters
- each taken only once 
- coming from s1 or s2.

SOLUTION:
- Combine 2 string
- Use set to remove the repeated
- Sort the set and return a string

```
def longest(s1, s2):
    return ''.join(sorted(set(s1+s2)))
```