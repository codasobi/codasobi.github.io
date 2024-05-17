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
If input is a string, then reverse it.

```
def solution(string):
    if isinstance(string, str):
        return string[::-1]
```