# Using Regular Expressions with `grep`

There are several regular expressions which can be used with `grep`

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


![image](https://user-images.githubusercontent.com/107522496/199698521-c084badd-0e59-4ca6-b4e3-e104d1d73128.png)

In the above example, it searches for words which begin with a "w" and have either an "o" or "e" after the "w".

Can also use `[]` to output a range of numbers
