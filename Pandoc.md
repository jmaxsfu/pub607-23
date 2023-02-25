# A Pandoc Tutorial

John Maxwell, Publishing @ SFU  
*originally a workshop for EBound Canada way back in 2014*



Beginning with a dead simple markdown file, in a plain text editor.


## Simplest possible:

    pandoc  test.txt -o test.html

The -o part tells Pandoc to put it's output ("o" for "output,"" get it?) into the filename you specify after the -o. If you don't specify and output file, it just spews output into your command shell, which is probably not what you want.

Open the resulting file up in your web browser -- and in your text editor. Note that it isn't a complete HTML document. We can ask it to include a proper header and footer -- make it a "standalone" document.

## Standalone: -s


    pandoc -s test.txt -o test.html

That's a little better. It now has a proper document "head," which specifies the title, and the character set, and things like that. Pandoc also adds a boilerplate stylesheet so it looks a bit more like something.

Let's add a stylesheet of our own instead of the default one.

## Add a stylesheet: -c

    pandoc -s test.txt  -o test.html -c stylesheet.css  

Pandoc is smart enough to reduce it's built-in boilerplate stylesheet to the bare minimum, and link in the external one that we use. We could call it "house style" and use it for all our books.


## Pandoc has multiple export formats.

If you don't tell it otherwise, Pandoc assumes it's converting markdown (text) to HTML. But you can specify output formats including html, rtf, odt, docx, icml, and many more. Use -t ("to")

    pandoc -t docx test.txt -o test.docx

## Pandoc has multiple import formats.

We can convert *from* many different formats as well using -f ("from")

    pandoc -f docx test.docx -o test.html

It's probably a good idea to use -t and -f explicitly all the time.

   pandoc -s -f markdown -t html test.txt -o test.html


## Thats the basics

You now know the basics of how to ask Pandoc to do conversions. The Pandoc manual, however, is 162 pages long. So there is a *lot* of nuance and flexibility on tap. You should spend some time browsing the Manual... https://pandoc.org/MANUAL.html


*********************************
((((((((((((((((()))))))))))))))))
&&&&&&&&&&&&&&&&&&&&&&&


# Pandoc to EPUB

If we can create HTML, we're already partway to EPUB. Not surprisingly, Pandoc can go the extra steps to creating EPUBs, and does a really good, thorough job of it. It can produce both EPUB2 and EPUB3 flavours (though the real difference between those two has more to do with what you put in the book).

Here's the basic method. Say we had a folder full of markdown files, one file per chapter. We can get pandoc to assemble them all, convert to HTML, assemble the package, set  metadata fields. Let's start simple, though: a three chapter book:

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





