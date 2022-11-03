# Using Regular Expressions with `grep`

There are several regular expressions which can be used with `grep`.

*  `.` this matches any single character 
*  `^` this mathces to the start of a line 
*  `$` this matches to the end of a line
*  `[abcde]` this matches character in the set provided 
*  `[^abcde]` this matches characters not in the set provided 
*  `[A-Z]` this matches the characters in the provided range 
*  `*` repeat previous expression 0 or more times
*  `\` escape 

---

# `.`

When using `.`, it represents a single character. 

![image](https://user-images.githubusercontent.com/107522496/199689107-56b1a609-0eb5-44fe-9607-187101cad3d0.png)

The example on the left highlights/returns patterns where the first three characters are "jun" and is followed by three more characters.
The example on the right highlights/returns patterns where the first letter is a "j" and is followed by two more characters.

However, when using this without the -w option, it may return matches which are spread across multiple words, for example:

![image](https://user-images.githubusercontent.com/107522496/199691995-7efbc4e6-d08a-4920-bf93-c02bace2c830.png)

To address this, we can use the `-w` option to only output patterns which are within one word, for example: 

![image](https://user-images.githubusercontent.com/107522496/199692432-e684d373-0541-480b-8213-b2d21c6bc6fd.png)

---

# `^`

The allows to search for lines which begin with a particular character. For example:

![image](https://user-images.githubusercontent.com/107522496/199695449-c7c718fa-949a-49aa-ad5b-0deabf22d913.png)

Can also show the line nummbers:

![image](https://user-images.githubusercontent.com/107522496/199695573-8d3df663-bbb9-45c2-b8bc-58b86985975f.png)

---

# `$`

The `$` symbol returns lines ending with the provided letter/pattern. 

![image](https://user-images.githubusercontent.com/107522496/199696556-128f0a97-c11c-44ed-89fb-b7764a9a3212.png)

---

# [abcde] 

When using `[]` with a set of characters, it returns patterns which include each of the characters within the set providedcontained in the `[]`. 

![image](https://user-images.githubusercontent.com/107522496/199705445-b80d5b5a-db3f-454f-9793-f0140d67b1f2.png)

In the above example, it searches for words which begin with a "w" and have either an "o" or "e" after the "w".

Another example is if we were looking for a word which begins with the letter "t" and has one of the following letters after it:

"aaeiou"

![image](https://user-images.githubusercontent.com/107522496/199712101-9a76ce8a-f958-4e7e-a392-76049a2bff81.png)

---

The below example is looking for words which begin with the letter "t" and Do NOT have either one of the following letters after it:

"aaeiou"

![image](https://user-images.githubusercontent.com/107522496/199712317-b135a58d-f8ee-44b3-98e3-3a3f7375103f.png)

---

Can also use `[]` to output a range of numbers:

![image](https://user-images.githubusercontent.com/107522496/199705539-40719142-b1d9-44fb-81f9-2a318cfd6c74.png)

---

# `[^]`

When using the `^` with `[]`, it returns patterns with the characters which are not within the provided set. For example:

![image](https://user-images.githubusercontent.com/107522496/199706212-4bcd783a-6b14-4f10-823b-99bf52c810f5.png)

---
 
 # Using `-E` option with `grep`
 
 The `-E` option can be used with `grep` to allow for extended regular expression syntax. This is the same as using `egrep`.
 
 Certain meta characters have a special meaning such as `?`, `+`, `(`, `\`, `{`, `)`. However, they can be used for their intended special meaning unless they are also escaped such as `\?`, `\+`, `\(`, `\|`, `\{`, `\)`. 
 
 But, if we use `grep` with the the `-E` option, they can be used for their special meaning without the `\`. 

For example, `grep "?" shortstory.txt -n` will search for the `?` character in the file, such as: 

 ![image](https://user-images.githubusercontent.com/107522496/199730851-b6e24f57-6402-4688-bc5c-fcdaecde1604.png)

 
 
 
 
 
 

