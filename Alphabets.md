# Alphabets, ASCII, and Unicode

"In the beginning was the *Word*"

- ...but it's all just ones and zeros, right?

::: notes :::

'Word' = Byte. 8 bits. 

How do we make bytes into something useful, like text? It's just a convention. A general agreement that this particular number -- represented as a byte, which, in 8-bits, is a number between 0 and 255, between 0 and 1111111, or (more conveniently, in hex) between 0 and FF -- stands for a particular letter of the alphabet.

Capital 'A' is 65 -- or 41 in hex (right?) -- 'B' is 66, and so on.
:::

## ASCII

The first really successful standard for this -- still with us today, after 55 years (1963) -- is ASCII. 

## {data-background="img/ASCII-Table.png"}


::: notes :::
How many letters in the alphabet? 26
x2 for upper and lowercase - 52
+ ten digits - 62
+ 30 punctuation marks - 92
+ 30-odd control codes for early systems - 127
+ one bit reserved for error control - 255

An alphabet with 127 possible characters. Sounds great, what could possibly go wrong?

A byte is 255 possibilities, so 127 is only half! So, easy to fix, right?

To get around the anglocentrism of that, various NON-standard schemes emerged. "Eight-bit extended character sets." Apple had one, Microsoft had a different one. Various standards were proposed (ISO 8859).

But a mess, generally. And non-Europeans were still utterly left out.
:::


## Unicode 

A solution, circa 1997

1,112,064 possible characters

::: notes :::
Real solution came in 1990s with Unicode, a full-scale, multi-byte replacement for ASCII.

1,112,064 theoretical "code points" -- enough for everybody.

First 256 corresponded to ISO 8859, for some measure of backward compatibility.

Implementations are still complex. This is literally like changing the alphabet from under us.


UTF-8, relatively speaking, made for an easy replacement for ASCII. Based on fixed 8-bit chunks (up to 4, for a million characters)

"A UTF-8 file that contains only ASCII characters is identical to an ASCII file."

Important piece of trivia (?) about Unicode:

A code-point is not a glyph. A code-point is an abstract representation of a character in the system. A glyph is an actual mark. So, individual glyphs -- for instance, **ligatures** are variable, and are actually defined in individual fonts. 

In all the fonts in the world, there are only a tiny handful that represent all of the Unicode space.

:::

## Unicode support

## {data-background="img/UnicodeGrow2b.png"}


::: notes :::
Unicode is supported by almost everything now. Mac OS X, Windows, Unix and Unix-derived operating systems. XML, HTML, and the Web and Internet standards.

BUT LEGACY SYSTEMS ARE STILL WITH US.. old software (esp critical databases) sometimes don't, and so stuff messes up.
:::

## {}

If you see little rectangles, or these things -- � ￼ ⸻ -- something in your toolchain has failed to support your Unicode.

## In Practice, really...

You can have "quotes"--- and dashes---in your résumé.


::: notes :::
What this means is that you can type accented characters, and curly quotes, and em-dashes, and greek, and whatever WITHOUT WORRYING about it.

You do not need to go look up the "character entity" replacement strings for these things.

E.g. you do not have to write `&mdash;` or U+2014 or `&#x2014;` (although these mostly work), you can just type an em-dash. On the Mac, shift-option-hyphen.
:::
