# About 'Regular Expression' parsing

Regular expressions refers to a tiny formal language for **describing** and then acting on (searching, replacing, etc.) regular patterns in text. It is the basis for all sorts of machine parsing of text.

aka "RegEx" or "regex," variously pronounced.

*aka* "GREP" after the venerable Unix tool (**G**lobal **R**egular **E**xpression and **P**rint). Technically, GREP is an application that uses regex. Since 2003 the OED has recognized 'grep' as both a noun and a verb.

"Wildcards" (as in MSWord) are a similar thing, but different; tends to be ad-hoc, as opposed to the formal and complete system that regex is.


Where will you find regex? Most importantly, in **text editors**. Sublime Text. BBEdit. Brackets. Whichever.

Regex is in lots of other software, including:

-   the Unix shell (which is also on your Mac)
-   OpenOffice/LibreOffice suite
-   Adobe Creative Suite
-   Google Docs
-   many DH tools
-   most every contemporary programming language/environment


## Basic concepts

A "regular expression" represents a **pattern** in text, codified in a tiny formal language.

The simplest kind of pattern is a **string** -- just a sequence of characters, like a word or a sentence, or a phone number. If we search for "foo" in a text, we will find instances of those three letters together.

But we can imagine other kinds of regular patterns that are more interesting and/or useful to us in our work: Like, all the things that are capitalized. Words that end in "ing." URLs. XML tags. Things that should be tabular but aren't. Phone numbers; dates; timecodes\...

Regex gives us a handle on such things. It allows us to describe abstract patterns in text, and then grab hold of those things and do things with them -- whether that's just finding them or doing something more active, like changing them, or collecting them, or doing some other processing on them.

This little formal language is actually very simple. There are only about 9 things to remember.

*(Chapter 8 in the BBEdit user manual is excellent -- the best single reference I've seen.\
As of April 2021, it's at https://s3.amazonaws.com/BBSW-download/BBEdit_13.5.6_User_Manual.pdf)*

# Regular Expression Syntax: 10 Building Blocks

## 1. Most characters just match themselves:

	A B C a b c

	1 2 3

	Horatio

	\t (tab)

## 2. Some **metacharacters** match more than just themselves

	\d  \w  \s  .

	(any digit, any 'word' element, any space, and any character at all)

## 3. **Quantifiers**

	?  *  +

	(optional; optional and repeatable; repeatable)
  
	(0 or 1; 0 or more; 1 or more)

## 4. **Alternation** (either\|or)

	a|b|c

	this|that

## 5. Parentheses group **sub-patterns**

	(apples|oranges)|vegetables

	(Jan|Feb|Mar|Apr|May) (\d+)

## 6. **Character classes** *(any one of this set...)*

	[abcedfg]

	[A-Za-z0-9]

## 7. **Position** operators

	^    $

	(match at start of line; end of line)

## 8. **Escaping** reserved characters (being literal instead of meta)

	\?   \.   \+

	\[   \(   \)

## 9. **Greedy** and **non-greedy** operators

	pattern+ (='greedy')

	pattern+? (='non-greedy')

	...very useful when matching pairs of quotation marks, or nested HTML tags.

## 10. **Replacement patterns** (for search & **replace**)

	\1  \2  \3

	= 1st, 2nd, 3rd (etc) sets of matched parentheses in search string can be *replaced* individually.

## 11. There is more...

There are some other pieces, but they're specific enough that you can google them if you need them.

## A note about line endings

Because of the tangled history of computing, there are actually THREE different legacy ways to represent a line break.[^1] Most software is smart enough to be entirely *agnostic* about them, so this doesn't present a problem 99% of the time.

But if we're searching, we have to be very specific, so you need to know that line breaks come in these flavours:

     \n    (the Unix-derived LF "line feed" character)  
     \r    (the old Apple CR "carriage return" character)
     \r\n  (microsoft's excellent compromise)

**Bottom line:** if you're searching for line endings with `\n` and it doesn't work, try `\r`. And vice-versa.


ALSO: Old text files -- such as those from Project Gutenberg -- split paragraphs into lines of 70-80 characters. More modern practice, assuming that software can 'wrap' lines automatically, will leave an entire paragraph to a single logical 'line' (that is, with an LF and/or CR at the end of the whole paragraph).

Again, being mindful of these distinctions will help you figure out how to make your regex patterns do what you want them to do.

## Learning Interactively

https://regex101.com/ is a website that provides an interactive environment for building regexes and testing them.

## Exercises and examples

Try your skill with these [Regex Exercises](RegexExercises.md)... better still, try your skill at saying that five times fast.

[^1]: See <https://en.wikipedia.org/wiki/Newline>