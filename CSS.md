# A CSS Tutorial

This is the smallest, shortest CSS primer you'll ever see.

## Basic syntax (note the punctuation):

A CSS file is a collection of declarations about what **things** (er, content objects) look like. We say which thing we mean by using a "selector" and then we tell it what we want by specifying "attributes" and "values". The punctuation is necessary: it basically goes like this:

      selector { attribute: value;  }

E.g., 

      h1 { font-size: 18pt; }

The **selector:**  specifies the thing that we're going to talk about. It can be an HTML **element** like `p` or `h1` or `blockquote`

		p

It can also refer to specific kinds of those elements, where they have named **classes** (as in `<p class="whatever">`. Or where they have a unique identifier:

		p.whatever

		p#uniqueID

You can also specify that the thing only counts if it appears in a particular context. For instance, `p` only if it appears within a `section` element, but not otherwise:

		section > p


**Attribute:** This specifies the quality of that thing we want to affect. Some examples:

		color: 

		width:

		margin-top:

		font-family:



**Value:** For the given attribute, this tells us the effect we want:

		color: blue;

		color: #0000ff;

		width: 100%;

		margin-top: 1em;

		font-family: Helvetica, "Akzidenz Grotesk";


Here are some further notes about [specificity in CSS]() -- getting at the thing you want.

Here are a couple of example CSS sheets, for your amusement and cribbing:

[simple.css]()  
[better.css]()  
[simpleEbook.css]() -- an simple css I wrote for an ebook project once.

