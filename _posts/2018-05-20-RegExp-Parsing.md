---
title: "RegExp Parsing"
layout: post
permalink: "/RegExp-Parsing.html"
---

Hello There !!
Simple Regular Expression parsing in python. It's kinda handy when you handling and manipulating the strings

What is RegExp AKA Regular Expressions:
---------------------------------------

The regular expressions are the way of extracting the pattern from the given string it's like a confusing at first as a beginner and after getting into it it's kinda handy and cool (A time saver)

This is kinda weird at first....!!!

Using the traditional method in python it didn't give that much of efficiency first loop through all words in a string and find a specific character and creating the new list comes under the cost of space,time...

How to work with RegExp:
------------------------

First, find the pattern you want to remove some set of string 

(The RegExp rule is defined upon yourself based on the use cases)

In my case, I want to parse the string without numerical as well as the special character no special character like 

```
0123456789~!@#$%&*()_+`-
```

It should only contain alphas in the string


Simple RegExp rules:
--------------------

Follow this table will give the simple basic rule to work with regexp

| Token         | Definition                     |
| ------------- |:-------------:                 |
| ^             | Start of strings               |
| $             | End of strings                 |
| .             |Any single Character            |
| \s             |    Any whitespace Character    |
| \S             |    Any non-whitespace character|
| \d             |    Any digit 0 to 9            |
| \D             |    Any non-digit               |
| \w             |    Any word character (letter, number & underscore)|
| \W             |    Any non-word Character      |
| [abc]         | Any single character a, b or c  |
| [^abc]        | Any character other than a, b or c        |
| [a-z]         | Character between(including) a to z       |


This table contains very basic to extract the regexp

Exp.
I want to parse just 

```
  hello@example.com ==> helloexamplecom
```

The simple expression is 

```
**r'\W'**
```

it removes all the special characters
This is how we write and use regexp parsing

Ex:

```

02 - I Bet My Life (Bastille Remix).mp3 ==> I Bet My Life (Bastille Remix).mp3 

```

The grammar how I wrote to parse the following first I remove 

- **02** then ,** (space)** ,**-**,** (space)** == '(02 - )'
- r'\d+\s+\D\s'

- *r = Escape character*
- *\d+ = digit and add one space after digit*
- *\s+ = white space and add one space after white space*
- *\D = Non digit*
- *\s = white space*

This is simple python program to parse the files name based on my use case

{% highlight python %}

import os
import re

cur_dir = os.getcwd()

dir_files = os.listdir(cur_dir)

for i in dir_files:    
    a = re.sub (r'\d+\s+\D\s', '',i) 
    #RegExp For Parsing '01 - All Eyes.mp3' -> 'All Eyes.mp3'    
    os.rename(i,a)

{% endhighlight %}

Here the simple parsing statement which converts the string to contain only
alphabets 

This how you can use the simple parsing using the RegExp.....!