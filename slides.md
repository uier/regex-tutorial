---
highlighter: shiki
theme: default
# lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.
---

# Regular Expression

An essential, powerful string processing tool for programmers.

<br>
<br>

presented by  
111 于子緯、111 莊博傑、112 周宗翰、113 張宇呈  
from Computer Science (CS)

<!--
Hi everyone
-->

---

# Regular Expression

or Regex/RegExp/RE in short

<Tweet class="h-50" id="1262408319282458625" />

---
layout: image-right
image: https://images.pexels.com/photos/164686/pexels-photo-164686.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260
---

# Imagine that...

1. Senior student
2. College of Science

<br><br><br><br>

<h3>How will you do that?</h3>

---

# Pseudo code

```
valid = empty mapping
for each sid
  if (sid is begin with '407') and (end with 's' or end with 'S')
    valid[sid] := yes
  else
    valid[sid] := no
```

<br><br><br>

<h3>Look really simple, right?</h3>

---
layout: statement
---

## But...Life isn't always easy

---
layout: image-right
---

<!-- 右邊要放陷阱卡的圖片 -->

# Trap Card ACTIVATED!

---

# Revised source code

```
valid = empty mapping
for each sid
  if ((sid is begin with '407') or (sid is begin with '408')) and
    ((end with 's' or end with 'S') or (end with 'h' or end with 'H'))
    valid[sid] := yes
  else
    valid[sid] := no
```

<br><br><br>

<h3>Well...It looks a little more complicated.</h3>

---
layout: cover
---

<!-- Add a cover photo -->

# Regex

---

# Refactor with regex

```
valid = empty mapping
for each sid
  if match sid with "40[78].*[sh]/i"
    valid[sid] := yes
  else
    valid[sid] := no
```

<br><br><br><br>

<!-- Add some meme? -->

---

# Why regex?

1. We don't need to re-compile the program.
2. Give user the ability to execute code is dangerous.
3. Engineers are lazy. We don't want to write anything twice.

---
layout: center
class: text-center
---

# `|` logical OR

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

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

# `\` escape special chars

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `[]` character sets

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---
layout: center
class: text-center
---

# `^` negation, do the opposite

<demo defaultPattern="a" defaultFlags="g" defaultText="The quick brown fox jumps over a lazy dog." />

---

# others
- `\d`, `\D`
- `\w`, `\W`
- `\s`, `\S`
- `\n`

---
layout: end
---

