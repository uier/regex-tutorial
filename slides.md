---
highlighter: shiki
theme: default
info: |
  ## Slidev Starter Template
  Presentation slides for developers.
title: Regular Expression
---

# Regular Expression

An essential and powerful string processing tool for programmers.

<br>
<br>

presented by  
111 于子緯、111 莊博傑、112 周宗翰、113 張宇呈  
from Computer Science (CS)

<!--
Good morning. We are students from NTNU Department of Computer Science and Information Engineering.

My name is 子緯, and our team member 博傑, 宗翰 and 宇呈.

In this presentation, we're going to introduce A VERY VERY COOL thing, REGULAR EXPRESSION, An Essential and Powerful string processsing tool for programmers.
-->

---

# Vocabulary in article

<br>

### 1. program
a series of instructions that can be put into a computer in order to make it perform an operation.

<br>

### 2. placeholder
a symbol or piece of text that can be replaced by particular pieces of information, used in mathematical expression or computer instruction.

<br>

### 3. character
a letter, number, or other symbol used in writing, especially in printed text or on a computer.

---

# Regular Expression

or Regex/RegExp/RE in short

<Tweet class="h-50" id="1262408319282458625" />

---

# Outline

1. What is Regex? & Why Regex?
2. The Syntax of Regex
3. Regex Challenges!
4. How does it work?

<!--
Firstly, we'll talk about what is regex? and why we need regex?

Secondly, we'll introduce the syntax of regex

Then, we'll have some challenges for you to exercise.

Finally, we'll briefly explain how regex works.

we'll also explain some technical term when needed.
-->

---
layout: image-right
image: ./images/student_list.png
---

# Imagine that...

1. Senior student (ID begins with '407')
2. College of Science (ID ends with 'S' or 's')

<br><br><br><br>

### How will you do that?

---

# Pesudo code

```python
for each student_id in student_list:
    if (student_id is begin with '407') and (student_id is end with 's' or end with 'S'):
        # valid ID
    else:
        # invalid ID
```

<br><br><br>

### Looks really simple, right?

<!--
Vocabulary  

- pesudo code
  : In computer science, pseudocode is not a programming language, it is not a valid code. but it can describe an algorithm to others. it is just plain desciption which looks like code.  
  example:
    The python code has 87% similarity of the pesudo code.
-->

---
layout: statement
---

## But...Life isn't always easy

---
layout: image-right
image: /images/trap-card.png
---

# Trap Card ACTIVATED!

1. Juinor students (ID begins with '408')
2. College of techonology and Engineering  
  (ID ends with 'H' or 'h')

<br><br><br>

### So..we need to rewrite the code.

---

# Revised source code

```python
for each student_id in student_list:
    if (((student_id is begin with '407') or (student_id is begin with '408')) and
        ((student_id is end with 's' or end with 'S') or (student_id is end with 'h' or end with 'H'))):
        # valid ID
    else:
        # invalid ID
```

<br><br><br>

### Well... It looks a little more complicated now.

---

# The problems

1. Engineers are lazy. We don't want to write similar code multiple times.
2. Engineers are lazy. We don't want to read code written by others.
3. You have to be able to write programs before you can search.
4. Give user the ability to execute code is dangerous.

<!-- 
Vocabulary

- compile
  : to change a computer program into a machine language.
  example:
    Please don't compile the identical source code twice and except
    the error will disappear. Go to fix your code!
-->

---
layout: section
---

# Regex

The life-saver of pattern matching

---

# Refactor with regex

```python
for each student_id in student_list:
    if match student_id with "40[78].*[sh]/i":
        # valid ID
    else:
        # invalid ID
```

<v-clicks>

```python
for each student_id in student_list:
    if (((student_id is begin with '407') or (student_id is begin with '408')) and
        ((student_id is end with 's' or end with 'S') or (student_id is end with 'h' or end with 'H'))):
        # valid ID
    else:
        # invalid ID
```

<div>
<br><br>

### Which one do you like?

</div>

</v-clicks>

<!-- 
Vocabulary

- refactor
  : (verb) restructure the source code of an application or piece of software
    so as to improve operation without altering functionality.  
  example:
    Sometimes, developers prefer to rewrite from scratch rather than
    refactor legacy code because they cannot even understand what they
    just wrote 3 days ago.
-->

---

# What is regex ?

- regex is a sequence of characters that specifies a search pattern.
- regex patterns are commonly used by string-searching algorithms
- e.g:
	- "find" or "find and replace" operations
	- input validation. 


<div class="flex space-x-5 mt-20">
  <img src="/images/regex-example-1.png" class="w-1/2">
  <img src="/images/regex-example-2.png" class="w-1/2">
</div>

---

# Where you can see it

<div class="flex justify-around mt-20">
  <div class="flex flex-col items-center space-y-3">
    <img src="/images/icon_msword.png" class="w-20">
    <div class="text-xl">MS Word</div>
  </div>
  <div class="flex flex-col items-center space-y-3">
    <img src="/images/icon_msexcel.png" class="w-20">
    <div class="text-xl">MS Excel</div>
  </div>
</div>

<div class="flex justify-around mt-20">
  <div class="flex flex-col items-center space-y-3">
    <img src="/images/icon_googledoc.png" class="w-20">
    <div class="text-xl">Google Docs</div>
  </div>
  <div class="flex flex-col items-center space-y-3">
    <img src="/images/icon_googlesheet.png" class="w-20">
    <div class="text-xl">Google Sheets</div>
  </div>
  <div class="flex flex-col items-center space-y-3">
    <img src="/images/icon_googleform.png" class="w-20">
    <div class="text-xl">Google Form</div>
  </div>
</div>


<div class="mt-12 text-xs">Icons made by <a href="https://www.flaticon.com/authors/pixel-perfect" title="Pixel perfect">Pixel perfect</a> and <a href="https://www.freepik.com" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a></div>

---
layout: image-right
image: /images/regex-coolguy.png
---

# Why must be regex?

- Clean (A pattern is worth a thousand codes)
- Standard (widely used)
- Be a Lifehacker!

---
layout: cover
---

# Syntax

---
layout: image-right
image: https://hackmd.io/_uploads/HJCcHURdt.png
---

# Quick Start

---

# Spectial Characters
- `. ` dot
- `()` parentheses
- `[]` brackets
- `{}` braces
- `\ ` backward slash, escape character
- `+ ` plus sign
- `* ` asterisk (people love calling it star)
- `? ` question mark
- `| ` pipe sign
- `^ ` caret

---
layout: center
class: text-center
---

# Normal Search

<demo defaultPattern="" defaultFlags="" defaultText="I have a fat cat called Matt as a pet. It caught a rat." />

<!-- 
let's match 'at' & add flag 'g' which means global, that is, match all occurence in text instead of only matching first one.
 -->

---
layout: center
class: text-center
---

# `.` dot
Matches any single character.

<demo defaultPattern="cap" defaultFlags="g" defaultText="I have a cap and a cup." />

<!-- 
then we can use dot to match any single character.
for example, /c.p/ matches both 'cap' and 'cup'.
 -->

---
layout: center
class: text-center
---

# `[]` Character Class
Matches any one of the enclosed characters

<demo defaultPattern="" defaultFlags="" defaultText="I have a fat cat called Matt as a pet. It caught a rat that weight 20 grams." />

<!-- 
we can use character class to contain multiple characters
like /[fcMr]at/
and we can use range, such as a-z, A-Z, 0-9, 0-1
also, in order to match dot, we need this [.]
 -->

---
layout: center
class: text-center
---

# `\` escaped
##### `\d` match digit, equivalent to `[0-9]`  
##### `\w` match alphanumeric character, equivalent to `[A-Za-z0-9_]`  
##### `\s` match white space character

<demo defaultPattern="\d" defaultFlags="g" :defaultText="'What is 24.0 \ 12.0 = ?\nIt\'s 2.\nCorrect!'" />

<!-- 
back slash means escape, what escape means is that the character after back slash is escaping from the original meaning
for example, another way to match a dot is using escape \.
 -->

---
layout: center
class: text-center
---

# `|` logical OR

<demo defaultPattern="" defaultFlags="g" :defaultText="'40747024s\n40847019S'" />

---
layout: center
class: text-center
---

# `()` Grouping

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `?` allow 0 or 1 times

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `*` allow 0 or many times

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `+` allow 1 or many times

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `{min, max}` explicit counts

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `^` negation, do the opposite

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

