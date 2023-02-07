# A Pandoc Tutorial

John Maxwell, Publishing @ SFU  
*originally a workshop for EBound Canada back in 2014*



Beginning with a dead simple markdown file, in a plain text editor.


## Simplest possible:

    pandoc  test.txt -o text.html

<div class="notes">
And here's the result. Note that it isn't a complete document. We can ask it to include a proper header and footer -- make it a "standalone" document.
</div>

## Standalone: -s


    pandoc -s test.txt -o text.html

<div class="notes">
Not terribly exciting, is it? But that's just the beginning.

Let's add a stylesheet.
</div>

## Add a stylesheet: *-c*

    pandoc -s test.txt  -o test.html -c stylesheet.css  




## Pandoc has multiple exports.

html, rtf ,odt, docx...

<div class="notes">
You can export to word-processor formats: RTF, ODT, .docx, though this seems entirely backwards to me.

In truth, I use this feature... when I have to submit an article to a journal than insists on a Word doc submission. I bet that's why MacFarlane put those in, too. There is also a substantial referencing system (citeproc) on tap as well. And a very nice footnoting system too.

</div>

## Pandoc to EPUB

<div class="notes">
If we can create HTML, we're already partway to EPUB. Not surprisingly, Pandoc can go the extra steps to creating EPUBs, and does a really good, thorough job of it. It can produce both EPUB2 and EPUB3 flavours (though the real difference between those two has more to do with what you put in the book).
</div>

## *The Memoirs of the Conquistador Bernal Diaz del Castillo, Vol 1*

<div class="notes">
Here's the basic method. Say we had a folder full of markdown files, one file per chapter. We can get pandoc to assemble them all, convert to HTML, assemble the package, set  metadata fields. Let's start simple, though: a three chapter book:
</div>

## Simplest possible:

    pandoc -s file1 file2...  -t epub3  -o file.epub

<div class="notes">
A glance at the excellent [Pandoc Users' Guide](http://johnmacfarlane.net/pandoc/README.html) tells us how to do lots of other things, too. Add your house stylesheet:
</div>

## Add an epub-stylesheet
    pandoc -s file1 file2... -t epub3 -o file.epub  
      --epub-stylesheet=house.css

## Add a cover image:

    pandoc -s  file1 file2...  -t epub3  -o file.epub  
      --epub-cover-image=cover.png 
      --epub-stylesheet=epub.css

<div class="notes">
Add metadata. There are two different ways: Here, specified in Dublin Core-style and stored in an external file: 
</div>

## Add metadata as XML:

    pandoc -s  file1 file2...  -t epub3  -o file.epub3  
       --epub-metadata=md.xml --epub-cover-image=cover.png 
       --epub-stylesheet=epub.css

<div class="notes">
There is another method, where you add the metadata in the source markdown file as well, in a "metadata block" that comes at the beginning. Possibly easier that way. It might look like this. We write all that stuff -- including the stylesheet and cover image -- in a file called frontmatter, and pass it along with the rest of the content.
</div>

## Add metadata in the source (much simpler!)

        pandoc -s metadata.txt file1 file2... -t epub3 
           -o file.epub

. . .

*(better)*

<div class="notes">
By default, Pandoc will break the EPUB into chapters where you have first-level headings. You can override that and set it to second-level heads if you choose, with yet another argument passed at the command.

See the power of this... we have a simple collection of text files; we can change them at will; then we simply re-build, and away we go:
</div>



## Pandoc to Print

<div class="notes">
Pandoc has a number of paths to PDF... beginning with LaTeX, a venerable computer typesetting system from the 80s/90s which was extremely well optimized for typesetting equations and formulae, and thus became the go-to system for typesetting mathematics and scientific papers. Lots and lots of scientific journals still use LaTeX. Students in math, physics, chem, learn how to do LaTeX... much better at formulae than any DTP tool, certainly historically, possibly still.

Pandoc also incorporates an ICML output, which is the 'story' format for Adobe InDesign. 'Place' the resulting .icml file directly in a blank InDesign template.
</div>





