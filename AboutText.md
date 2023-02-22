# A History of Digitized Text

What's so special about text?

It *matters* what kind of stuff is in the file. A binary file (like an image, or audio, or an InDesign document) is, fundamentally hard to edit. It needs to be reconstituted by some application into a workable format -- for instance, in an audio editing application -- then saved back into the file format.

Text files -- and text-based data -- on the other hand, are editable as they are, because their structure corresponds exactly (or at least closely) to what they represent. A plain text file is made up exactly of the letters you read when you read it. Editing the file is identical with editing the text.

Text is special. This goes beyond the mechanics of files and file formats. Text is special because it's uniquely editable, changeable, mutable. What's that? You thought it was special because it was unchanging! But that's *print*, not *text*. The "text" comes into being at the point when Gutenberg makes the type "moveable."

Text can be edited; it can be parsed; it can be processed in ways that are incredibly broadly understood, literally by every literate person. Compare that to all that's required to edit two seconds out of a video file -- or your sister's ex from a family photo.

(Actually, when we have systems that *generate* audio or video, we typically interact with it via 'notation,' which is intended to work sort of like text. Think about music scores, for instance. And XML, more about which below...)

Text is special because we know how to process it, and so making computers process text is an extension of our own understanding, as opposed to something unique that has to be invented (like Photoshop or something).

## A tale of two paradigms

Interestingly, the history of how we think about text in computers has two parallel traditions, very different in approach. These intersect here and there, but are almost two distinct *paradigms*.

The first tradition starts with text files, and builds structure into these files in order to deal with things like formatting, metadata, and so on. This tradition comes out of old-school typesetting and leads through Standard Generalized Markup Language (SGML, from the 1980s), HyperText Markup Language (HTML, early 1990s), to eXtensible Markup Language (XML, from the late 1990s). It is the approach that underlies the Web and most "digital publishing" formats.

In this way of thinking, the text and its innate structures are of paramount importance, and things like formatting and layout are secondary; they need to be layered onto the underlying text structures. This approach is extremely well suited to accessibility, as a single text can be manifest in different formats for different audiences or different contexts.

The second tradition, largely invented at Xerox PARC in the 1970s, makes page layout primary, and everything else is secondary. This tradition begins with "Desktop Publishing" (DTP) leading through word processors and software like PageMaker, QuarkXpress, and InDesign, and reaches its full express in the PDF -- which is a perfect virtual image of a page. The goal is "WYSIWYG" -- *what you see is what you get* -- that what you see on the computer screen is what you'll get on the printed page. This tradition has been dominant in publishing since around 1990, and it utterly replaced traditional typesetting. 



But the page-first paradigm presents all sorts of difficulties for multiple formats, and especially for accessibility, since the underlying text needs to be extracted from what the software is adapted to: page layout. 

In 2023, we live in a world where these two traditions co-exist, but only interact with some difficulty (as seen with the "born-accessible book"). There are ways of moving between the two approaches; being aware that there ARE two distinct approaches is the first step to that. You would be surprised how few people on this planet really understand this.


## The Elusive Goal of Interoperability 

The goal of **interoperability** -- or, to put it conversely: avoiding **lock-in** or forced dependence on a particular vendor or platform -- has been approached in a couple of different keys. Foremost is the idea of an open, explicitly described file format, as opposed to a file format whose internal structure is only known or fully understood to the vendor. 

Word's .doc and .docx formats, for instance, are well enough known for file translators to exist (you can import Word files into InDesign, for instance), but the file format suits Microsoft's business interests above all. The insides of an .indd file are almost completely opaque.

Text files are an excellent choice for open file formats, because text files are, at least theoretically, readably by human beings. As a result, lots of open formats are at their base levels text files. More sophisticated structures are built up within them using standardized conventions.



## Formatting

Back to text for publishing... the XML only tells us is what is *in* the text -- its structures and parts -- but we can use those structures as hooks for formatting rules.

A **stylesheet** defines formatting rules for named structures in the text. This works in Microsoft Word, in Adobe InDesign, in your web page, and in XML more generally. 

We define rules that say things like: body copy should be 10pt Garamond on 14pt line spacing, with a 56 em line length. First-level heads should be 18pt Gill Sans -- unless they appear in the context of a sidebar, in which case it should be 12pt instead. 

A stylesheet like this produces a "templated" design -- as opposed to being hand-crafted or bespoke. The power of a templated design is that the same stylesheet can be applied to many documents. It also means that one stylesheet can be swapped for another -- changing the formatting of a document without changing the text itself. Such an approach may be useful in the context of accessibility, or in multi-mode delivery.

This formal separation of the text (and its named structures) and the formatting rules is one example of the concept of "separation of concerns," which is a more general design pattern. We have had separation of concerns in publishing since Gutenberg put moveable type into practice, and the abstract idea of a text -- in the form of a **marked up** manuscript that compositors would use in typesetting -- came to drive formatting. 

This separation of the *platonic* ideal of the text from any particular printed instance of it has both delighted and vexed scholars and critics ever since. At this very point, when the text becomes *abstract and mutable*, it also becomes capable of *fixity and durability* over centuries owing to its production and distribution in mass quantities.

Ironically, the Desktop Publishing tradition, embodied today in InDesign, runs completely counter to this idea... in InDesign, format *is* structure, not the other way around.


