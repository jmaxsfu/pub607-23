# A Pandoc Tutorial

John Maxwell, Publishing @ SFU  
*originally a workshop for EBound Canada way back in 2014*

---

One of the key pieces of software we will use with markdown is **Pandoc** -- which bills itself as the "universal document converter." 

<https://pandoc.org>

Pandoc is not the only tool that will convert markdown -- indeed there are hundreds of those -- but it is the best, and the most flexible.

Pandoc was originally designed as a markdown-to-HTML conversion tool, but it has been *generalized* to work with dozens of different input and output formats.

What that means is that it takes any structured (or even semi-structured) document format, and parses it into an internal representation. That internal representation can then be re-written in any other structured document format.

Pandoc is extremely high-quality software, and it is *exquisitely* well documented. I have often said that "a close reading of the Pandoc user manual would constitute a whole course in document production." Since you're currently taking a course in ebook production, it would be a good idea to at least familiarize yourself with Pandoc's incredibly well-written User's Manual: 

<https://pandoc.org/MANUAL.html>

Pandoc, it must be said, has a command-line interface. That means you use it by typing commands into a command shell, like it's 1983 all over again. You have one of these, though: on your Mac, it's called "Terminal." On Windows, it's called "Powershell."

I know, it's old, and it makes you feel like you're in an 80s movie. But the command-line interface actually really works incredibly well, especially for text processing, because it was invented for text processing. If you want to be one of the cool kids, you'll play with the preferences in your shell so that it's green type on a black background. Embrace your inner geek! 


Here's a [Command-shell cheat sheet](Commands.md)


## Working with Pandoc


Beginning with a dead simple markdown file...

We talk to Pandoc by issuing commands in our command shell. The examples below assume you are "in" the same folder where the files are. If not, you need to `cd` into that folder, so that when you `ls` to see the files there, you see the ones you want to work with. 

The basic format for Pandoc commands is like so:

    pandoc inputFile -o outputFile 

There are other options we can (and will) specify, though, by writing them in the age-old Unix way, with a hyphen and a letter, like "-o" above. Pandoc also has more verbose, explicit alternatives where you type two hyphens and then a specific label, followed by the equal sign, and then the option you want. That's harder to describe than it is to show. 

In the examples below, I'll show both ways of setting these options... in practice, it's easier to type the shorter version, but the longer version is useful for getting familiar with them.


## Simplest possible:

    pandoc  test.md -o test.html  
    pandoc  test.md --output=test.html

These two versions are identical; I'm including both for the sake of clarity.

The **-o** part tells Pandoc to put it's output ("o" for "output,") into the filename you specify after the -o. If you don't specify and output file, it just spews output into your command shell, which is probably not what you want. If you specify a file that already exists, it will be over-written. If you specify a file that doesn't exist, it'll get created.

Open the resulting file up in your web browser -- and in your text editor. Note that this simples possible example isn't a complete HTML document -- it's just content in HTML format. 


## Standalone: -s

We can ask it to include a proper header and footer -- make it a "standalone" document.

    pandoc -s test.md -o test.html  
    pandoc --standalone test.md --output=test.html

That's a little better. It now has a proper document "head," which specifies the title, and the character set, and things like that. Pandoc also adds a boilerplate stylesheet so it looks a bit more like something.


## Add a stylesheet: -c

Let's add a stylesheet of our own instead of the default one.

    pandoc -s test.md  -o test.html -c stylesheet.css    
    pandoc -s test.md  -o test.html --css=stylesheet.css  

Pandoc is smart enough to reduce it's built-in boilerplate stylesheet to the bare minimum, and link in the external one that we use. We could call it "house style" and use it for all our books.


## Pandoc has multiple export formats.

If you don't tell it otherwise, Pandoc assumes it's converting markdown (text) to HTML. But you can specify output formats including html, rtf, odt, docx, icml, and many more. Use -t ("to")

    pandoc -t docx test.md -o test.docx
    pandoc --to=docx test.md -o test.docx


## Pandoc has multiple import formats.

We can convert *from* many different formats as well using -f ("from")

    pandoc -f docx test.docx -o test.html  
    pandoc --from=docx test.docx -o test.html

You can go back to markdown, too.

    pandoc -f html -t markdown test.html -o test.md 
    pandoc --from html --to markdown test.html -o test.md

## Thats the basics!

You now know the basics of how to ask Pandoc to do conversions. The Pandoc manual, however, is 162 pages long. So there is a *lot* of nuance and flexibility on tap. You should spend some time browsing the Manual... https://pandoc.org/MANUAL.html


# Pandoc to EPUB - Building your EBook with Pandoc

If we can create HTML, we're already most of the way to EPUB. Not surprisingly, Pandoc can go the extra steps to creating EPUBs, and does a really good, thorough job of it. It can produce both EPUB2 and EPUB3 flavours.

The sensible way to proceed is to prepare the content as markdown, and to develop a basic stylesheet while converting to HTML only -- this allows very easy proofing and feedback in your web browser. Once you're happy with the editing, though, you can shift to producing EPUB, which is more cumbersome to proof.

It's common to produce ebooks with one chapter per file. The reasons have to with ease of use, and probably a little bit about keeping the files small and fast to load, too. But you don't have to; you can easily produce an EPUB with all the content in a single text file; Pandoc uses the Headers (level 1 or 2, typically) to build the chapter navigation.

So we'll proceed with the idea of an ebook as a folder full of files. This example will have one markdown file per chapter. We can get pandoc to assemble them all, convert to HTML, assemble the package, and set the metadata fields. 

## Simplest possible:

    pandoc -s chapter1.md chapter2.md chapter3.md  -t epub3  -o book.epub

You can open this file up in Thorium Reader or Apple Books.app or whatever.

## Add a stylesheet

We can add our house stylesheet just the same as we did with our HTML conversions:

    pandoc -s chapter1.md chapter2.md chapter3.md  -t epub3  -o book.epub  -c stylesheet.css

## Add a cover image:

Our book shows up in the ereader with a blank cover. Let's fix that: 

    pandoc -s chapter1.md chapter2.md chapter3.md  -t epub3  -o book.epub -c stylesheet.css --epub-cover-image=cover.png 


## Add metadata as XML:

Notice that Pandoc has been complaining that our book has no title. It's also missing other information, like author, publication date, and so on.

There are two different ways: One is where metadata is written in Dublin Core XML and stored in an external file. This option probably makes sense if your company already has an ebook workflow and generates metadata as XML

    pandoc -s chapter1.md chapter2.md chapter3.md  -t epub3  -o book.epub -c stylesheet.css --epub-cover-image=cover.png --epub-metadata=md.xml

## Add metadata in the source (much simpler!)

There is a simpler method, where you add the metadata in the source markdown file as well, in a "metadata block" that comes at the beginning. 

We'll just pass the metadata as another content file. 

    pandoc -s frontmatter.md chapter1.md chapter2.md chapter3.md  -t epub3  -o book.epub -c stylesheet.css --epub-cover-image=cover.png 

Note that you could also pass the cover image and the stylesheet in this metadata block -- and it would clean up this Pandoc command a whole bunch!




## Pandoc to Print

Pandoc has a number of paths to PDF... beginning with LaTeX, a venerable computer typesetting system from the 80s/90s which was extremely well optimized for typesetting equations and formulae, and thus became the go-to system for typesetting mathematics and scientific papers. Lots and lots of scientific journals still use LaTeX. Students in math, physics, chem, learn how to do LaTeX... much better at formulae than any DTP tool, certainly historically, possibly still.

Pandoc also incorporates an ICML output, which is the 'story' format for Adobe InDesign. 'Place' the resulting .icml file directly in a blank InDesign template.

We'll demo this.





