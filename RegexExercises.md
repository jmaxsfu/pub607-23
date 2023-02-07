(back to [Regular Expressions]())

## 1. Numbers of numbers

`\d+` will match any number, regardless of how many digits

How else could you write this to ensure that it is only a one- or two-digit number?


## 2. URLs and other regular-looking text

Find all the URLs in the file [bibliography.txt]().

Can you find all the http URLs as well as the DOIs?


## 3. Phone number normalization

[phoneNumbers.txt]() -- Find variously formatted telephone numbers and make sure they have the same kind of dashes and punctuation.


In groups... the following challenges:

## 4. Find messy HTML tags and tidy them up (all lowercase)

in the file [HTML.html]() -- HTML tags are supposed to be all lowercase. Can you find and fix the tags in this file? 

Use `\L` in front of your replacement strings to convert them to lowercase.



## 5. Cleaning up Project Gutenberg texts

(apologies to Tara for not having this ready two weeks ago)

See the file: [AliceDownRabbitHole.txt]() -- which is just the first bit of Lewis Carroll's *Alice's Adventures in Wonderland*.

Find where the author typed 4 (or 5, or 3) spaces at the beginning of a paragraph, and get rid of those. Paragraph indents should be handled by a stylesheet, not by typing extra characters.

Find the quotation marks -- which are \` and ' -- and change that to proper quotation marks.

Find where there are two spaces after a period and reduce to one.

Find underlined phrases and change them to... uppercase? Or use asterisks to indicate italics instead?  






