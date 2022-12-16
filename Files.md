# PUB 607 Fundamentals

## On File Management

A file is a metaphor for a structured bundle of data in a computer. Files do not actually exist in your computer, on it's hard drive (nor is the disk "hard" even). It's a metaphor that guides a set of behaviours around how we deal with files.

The file idea, more or less, dates to the late 1960s, early 1970s, and was popularized through the spread of the Unix operating system (which is still with us). We still think largely in terms of files, although different metaphors are becoming more common: streams; queries; 

Files are organized in Filesystems; the one we all take for granted in the hierarchical file system, where there is a hierarchal set of "folders" that uniquely locate and organize files. It does NOT have to be this way.

Inside a file is data... typically, the "header" of the file is a bundle of data that identifies the file type and provides some basic metadata so that your operating system (and you) can make sense of it. After that is a bundle of data that contains the "content" of the file: a text, an image, a sound, your taxes, a set of database relations.

For the most part, files are DUMB. They don't *do* anything; they sit there passively until operated on by an application, which can open, read, edit, and/or save the file.

There are as many **file types** as there are pieces of software. More or less. Which is to say, gazillions. Standards are the exceptions, not the rule, so we find every different version of a word processor has its own file type... which results in files being unusable, or at least only partially usable, if they aren't used by the exact application that it was designed for.

There are, notably, a few important standards, where file types work across a number of different applications:

Text files, made up only of lines of text characters, was the old standard for Unix files; these are, handily, mostly human-readable. Sometimes text files have a specific internal format: e.g., .csv spreadsheets

Image, sound, and video files that we pass around on the Internet (JPGs, PNGs, MP3s, MOVs, etc.), since the early Internet was pluralistic enough to demand open file formats that different tools and applications could use.

XML files, which are text files at the bottom layer, are theoretically openable and usable by any XML-aware application. IN reality it's not quite so simple.

Defacto common standards like .docx files or .pdf files are sort-of open and sort of interoperable, but they are still largely controlled by Microsoft and Adobe. They have achieved standard-like status because they are ubiquitous.

File naming is, for the most part, unregulated. There is a common, unenforced standard whereby we use a particular 3- or 4-letter code at the end of the filename to indicade the file type. But it's not really a standard; it's just how most people and a fair bit of software recognizes things.

What you put before the dot is up to you. The trouble with this, obviously, is that your computer (and your inbox) eventually fills up with untitled.docx files or final.xlsx, or worse: FINALfinal.pdf.

It's pretty common for people to use short, easily typed filenames and then rely on the enclosing folder for context. Which of course falls apart as soon as you take the file out of that folder and send it to someone.

Regular computer filesystems, for the most part, do not track their history. If I have two files named FINAL.docx, I might have a clue about which one is FINAL-er than the other by comparing the date in the file metadata; but that date might reflect when the file was sent to me rather than when it was actually edited. 

There ARE systems for tracking changes -- or versions -- in files and filesystems, and they are worth using. Generally, this means going to the trouble of doing it, though.

The good old workaround for this is to embed version information manually in the filename, like FINAL-JMaxDec13.docx -- It's hardly foolproof, but it might be better than nothing.



## Content Management concepts and software

Part of what's so successful about the "file" metaphor is that it allows us to think of digital things as if they were paper documents. Some implications of that are that we don't tend to think of a file existing in more than once place at once. We also don't really think of them as dynamic. If a file changes we like to think of it as a new version of that file, as opposed to the same file.

Content management systems break some of these conceptual limitations. Instead of files proliferating in hierarchies of folders -- on my computer, on your computer, in your inbox, in my inbox -- we keep a file in one central online place, and anyone who needs to see it, work on it, etc. comes to it. So multiple people can all be accessing the same file at once. That necessitates keeping track of changes to the file -- if you and I are both editing it, what happens, and when?

There are lots of different kinds of content management systems. Wordpress is one kind. Dropbox is another kind. Github is another. Each makes slightly different trade-offs between the kind of flexibility it offers, against how far it breaks the paper-document metaphor. 

Wordpress very much keeps a single, centralized copy of a document (for instance, a post), but it makes the change history of that document easy to see and manage. Dropbox also keeps a change history, but it mostly hides it away, so your file in Dropbox looks a lot more like a file on your own computer. Github uses both local files -- in your own folder hierarchy, and centrally held files, managing version history across these (and across multiple users), and keeps all the different versions in sync; it's harder to get your head around, but is super powerful and flexible as a result.






## File types and what they are

## A History of Digitized Text

PDF vs XML; 

## The Elusive Goal of Interoperability 

XML as a data exchange standard

(and mention onix here)
