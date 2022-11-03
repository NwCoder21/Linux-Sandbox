# Using Regular Expressions with `grep`

There are several regular expressions which can be used with `grep`

## When using the `.`, it represents a single character. 

![image](https://user-images.githubusercontent.com/107522496/199689107-56b1a609-0eb5-44fe-9607-187101cad3d0.png)

The example on the left highlights/returns patterns where the first three characters are "jun" and is followed by three more characters.
The example on the right highlights/returns patterns where the first letter is a "j" and is followed by two more characters.

However, when using this without the -w option, it may return matches which are spread across multiple words, for example:

![image](https://user-images.githubusercontent.com/107522496/199691995-7efbc4e6-d08a-4920-bf93-c02bace2c830.png)

To address this, we can use the `-w` option to only output patterns which are within one word, for example: 

![image](https://user-images.githubusercontent.com/107522496/199692432-e684d373-0541-480b-8213-b2d21c6bc6fd.png)

---





