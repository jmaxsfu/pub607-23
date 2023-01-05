# PUB 607 Fundamentals

## On File Management

A file is a **metaphor** for a structured bundle of data in a computer. Files do not actually exist in your computer, or on its hard drive (which is not in fact hard). It's a metaphor that shapes a set of behaviours around how we deal with files. The metaphor is closely related to the idea of "documents," but not exactly equivalent.

The file idea, more or less, dates to the late 1960s, early 1970s, and was popularized through the spread of the Unix operating system (which is still with us). We still think largely in terms of files, although alternative metaphors (or patterns) are becoming more common: streams; queries; things pulled together on the fly out of databases.

Files are typically organized in **Filesystems**; the one we all take for granted is the "hierarchical file system," where there is a hierarchical set of "folders" that uniquely locate and organize files. It seems natural because it's been with us for decades, but it's not natural, and it does NOT have to be this way.

Inside a file is data... typically, the "header" of the file is a bundle of data that identifies the file type and provides some basic metadata so that your operating system (and you) can make sense of it. Following that is a bundle of data that represents the "content" of the file: a text, an image, a sound, your taxes, a set of database relations, or whatever.

For the most part, files are DUMB. They can't *do* anything; they sit there passively until operated on by an **application**, which can open, read, edit, manipulate, and/or save the file.

There are as many **file types** as there are pieces of software, more or less. Which is to say, gazillions of them. File standards are the exceptions, not the rule, and so every different version of a word processor has its own file types. The result is files that end up being unusable, or at least only partially usable, if they aren't used by the exact application that they were designed for.

There are, notably, a handful of important standards, where file types work across a number of different applications and aren't bound to a single app:

**Text files**, made up only of lines of text characters. This was the old standard for Unix files, and these are, handily, mostly human-readable. Sometimes text files have a specific internal format: e.g., .csv spreadsheets.

**Image, sound, and video files** that we pass around on the Internet (JPGs, PNGs, MP3s, MOVs, etc.). Since the early Internet was pluralistic enough to demand **open file formats** that a variety of different tools and applications could all use. These are structured bundles of, for the most part, *sampled* data about images, sounds, etc. More about this below...

**XML files**, which are text files with specific structures expressed in them. XML files are theoretically openable and usable by any XML-aware application. In reality it's not quite so simple.

**Defacto common standards** like .docx files or .pdf files are *sort-of* open and *sort of* interoperable, but they are still largely controlled by Microsoft and Adobe. They have achieved standards-like status because they are ubiquitous.

## So many files! How can I manage?

**File naming** is, for the most part, unregulated. There is a common practice wherein we use a particular 3- or 4-letter code at the end of the filename to indicade the file type (e.g. ".txt" or ".pdf"). But it's not a formal standard; it's just how most people and a fair bit of software recognizes things.

What you put before the **dot** in a file name is up to you. The trouble with this practice, obviously, is that your computer (and your inbox) eventually fills up with `untitled.docx` files or `final.xlsx`, or worse: `FINALfinal.pdf`.

It's pretty common for people to use short, easily typed filenames and then rely on the enclosing folder name for context. This, of course, falls apart as soon as you take the file out of that folder and send it to someone.

Regular computer filesystems, for the most part, do not track the history of changes to files. If I have two files named `final.docx`, I might have a clue about which one is final-er than the other by comparing the date in the file metadata; but that date might only reflect when the file was *sent to me* rather than when it was actually edited. 

There *are* systems for **tracking changes** -- or **versions** -- in files and filesystems, and they are definitely worth using. Generally, this means going to the trouble of doing so, though.

A good old DIY workaround for this is to embed version information directly in the filename, like `final-JMax-Dec13.docx` -- It's hardly foolproof, but it might be better than nothing.

## Content Management concepts and software

Part of what's so successful about the "file" metaphor is that it allows us to think of digital things *as if they were paper documents*. One implication of this practice is that we don't tend to think of a file as existing in more than once place at once. We also don't really think of them as dynamic. If a file changes, we like to think of it as a new version of that file, as opposed to the same file.

**Content management systems** (CMS) break some of these conceptual limitations. Instead of files living in hierarchies of folders -- on my computer, on your computer, in your inbox, or in my inbox -- a CMS keeps a file in one central online place, and anyone who needs to see it, work on it, etc. comes to it, rather than a copy of the file travelling to them. Therefore multiple people can all be accessing the same file at once. That necessitates keeping track of changes to the file -- if you and I are both editing it, what happens, and when?

There are lots of different kinds of content management systems. **Wordpress** is one kind. **Dropbox** is another kind. **Github** is another. Each makes slightly different trade-offs between the kind of flexibility it offers, against how far it breaks the paper-document metaphor. 

**Wordpress** very much keeps a single, centralized copy of a document (for instance, a post), but it makes the change history of that document easy to see and manage. **Dropbox** also keeps a change history, but it mostly hides it away, so your file in Dropbox looks and acts a lot more like a regular old file on your own computer. **Github** has both local files -- in your own folder hierarchy -- and centrally managed files, tracking the change history across all of these (and across multiple users), and keeping all the different versions in sync; it's harder to get your head around initially, but it is super powerful and flexible as a result.




------------------------





## A History of Digitized Text

What's so special about text?

It *matters* what kind of stuff is in the file. A binary file (like an image, or audio, or an InDesign document) is, fundamentally hard to edit. It needs to be reconstituted by some application into a workable format -- for instance, in an audio editing application -- then saved back into the file format.

Text files -- and text-based data -- on the other hand, are editable as they are, because their structure corresponds exactly (or at least closely) to what they represent. A plain text file is made up exactly of the letters you read when you read it. Editing the file is identical with editing the text.

Text is special. This goes beyond the mechanics of files and file formats. Text is special because it's uniquely editable, changeable, mutable. What's that? You thought it was special because it was unchanging! But that's *print*, not *text*. The "text" comes into being at the point when Gutenberg makes the type "moveable."

Text can be edited; it can be parsed; it can be processed in ways that are incredibly broadly understood, literally by every literate person. Compare that to all that's required to edit two seconds out of a video file -- or your sister's ex from a family photo.

(Actually, when we have systems that *generate* audio or video, we typically interact with it via 'notation,' which is intended to work sort of like text. Think about music scores, for instance. And XML, more about which below...)

Text is special because we know how to process it, and so making computers process text is an extension of our own understanding, as opposed to something unique that has to be invented (like Photoshop or something).

### A tale of two paradigms

Interestingly, the history of how we think about text in computers has two parallel traditions, very different in approach. These intersect here and there, but are almost two distinct *paradigms*.

The first tradition starts with text files, and builds structure into these files in order to deal with things like formatting, metadata, and so on. This tradition comes out of old-school typesetting and leads through Standard Generalized Markup Language (1980s) to eXtensible Markup Language (XML) and HyperText Markup Language (HTML) in the 90s and beyond. It is the approach that underlies the Web and most "digital publishing" formats.

In this way of thinking, the text and its innate structures are of paramount importance, and things like formatting and layout are secondary; they need to be layered onto the underlying text structures. This approach is extremely well suited to accessibility, as a single text can be manifest in different formats for different audiences or different contexts.

The second tradition, largely invented at Xerox PARC in the 1970s, makes page layout primary, and everything else is secondary. This tradition begins with "Desktop Publishing" (DTP) leading through word processors and software like PageMaker, QuarkXpress, and InDesign, and reaches its full express in the PDF -- which is a perfect virtual image of a page. This tradition has been dominant in publishing since around 1990, and it utterly replaced traditional typesetting. 

But the page-first paradigm presents all sorts of difficulties for multiple formats, and especially for accessibility, since the underlying text needs to be extracted from what the software is adapted to: page layout. 

In 2023, we live in a world where these two traditions co-exist, but only interact with some difficulty (as seen with the "born-accessible book"). There are ways of moving between the two approaches; being aware that there ARE two distinct approaches is the first step to that. You would be surprised how few people on this planet really understand this.


## The Elusive Goal of Interoperability 

The original markup language standards SGML, HTML, and early XML) were designed for publishing; they were concerned with marking up texts for processing, printing, searching, and distribution online. But the "generalized" idea (the G in SGML, and the X in XML) means these ways of treating text become useful as notation systems to describe data structures.

'''

### **HTML** -- that is, prose text for publishing, in a website, in an ebook, etc.:

<html>
	<body>
		<section id="pub-607-fundamentals" class="level1">
			<h1>PUB 607 Fundamentals</h1>
		<section id="on-file-management" class="level2">
			<h2>On File Management</h2>
			<p>A file is a <strong>metaphor</strong> for a structured bundle of data in a computer. Files do not actually exist in your computer, or on its hard drive (which is not in fact hard). It’s a metaphor that shapes a set of behaviours around how we deal with files. The metaphor is closely related to the idea of “documents,” but not exactly equivalent.</p>
			<p>The file idea, more or less, dates to the late 1960s, early 1970s, and was popularized through the spread of the Unix operating system (which is still with us). We still think largely in terms of files, although alternative metaphors (or patterns) are becoming more common: streams; queries; things pulled together on the fly out of databases.</p>
			<p>Files are typically organized in <strong>Filesystems</strong>; the	one we all take for granted is the “hierarchical file system,” where there is a hierarchical set of “folders” that uniquely locate and organize files. It seems natural because it’s been with us for decades, but it’s not natural, and it does NOT have to be this way.</p>
			...


### SVG, Scalable Vector Graphics, a web-portable graphics standard:

<svg width="467" height="462">
  <rect x="80" y="60" width="250" height="250" rx="20"
      style="fill:#ff0000; stroke:#000000;stroke-width:2px;" />
  <rect x="140" y="120" width="250" height="250" rx="40"
      style="fill:#0000ff; stroke:#000000; stroke-width:2px;
      fill-opacity:0.7;" />
  <rect x="140" y="120" width="250" height="250" rx="40"
      style="fill:#00ff00; stroke:#0000cc; stroke-width:5px;
      fill-opacity:1.0;" />
</svg>


### RSS, or syndication feeds for podcasts, blogs, news headlines, etc:

<rss version="2.0">
  <channel>
    <title>Dafna's Zebra Podcast</title>
    <itunes:owner>
        <itunes:email>dafna@example.com</itunes:email>
    </itunes:owner>
    <itunes:author>Dafna</itunes:author>
    <description>A pet-owner's guide to the popular striped equine.</description>
    <language>en-us</language>
    <link>https://www.example.com/podcasts/dafnas-zebras/</link>
    <item>
      <title>Top 10 myths about caring for a zebra</title>
      <description>Here are the top 10 misunderstandings about the care, feeding, and breeding of these lovable striped animals.</description>
      <pubDate>Tue, 14 Mar 2017 12:00:00 GMT</pubDate>
      <enclosure url="https://www.example.com/podcasts/dafnas-zebras/audio/toptenmyths.mp3"
                 type="audio/mpeg" length="34216300"/>
      <itunes:duration>30:00</itunes:duration>
      <guid isPermaLink="false">dzpodtop10</guid>
    </item>
    <item>
      <title>Keeping those stripes neat and clean</title>
      <description>Keeping your zebra clean is time consuming, but worth the effort.</description>
      <pubDate>Fri, 24 Feb 2017 12:00:00 GMT</pubDate>
      <enclosure url="https://www.example.com/podcasts/dafnas-zebras/audio/cleanstripes.mp3"
                 type="audio/mpeg" length="26004388"/>
      <itunes:duration>22:48</itunes:duration>
      <guid>dzpodclean</guid>
    </item>
  </channel>
</rss>

ONIX, bibliographic data for the book supply chain

<ONIXMessage release="3.0">
	<Product>
		<ProductIdentifier>
			<ProductIDType>15</ProductIDType>
			<IDValue>9789999999991</IDValue>
		</ProductIdentifier>
		<DescriptiveDetail>
			<TitleDetail>
				<TitleType>01</TitleType>
				<TitleElement>
					<TitleElementLevel>01</TitleElementLevel>
					<TitleText>My Dreary Life</TitleText>
					<Subtitle>A Meandering Tale</Subtitle>
				</TitleElement>
			</TitleDetail>
			<Contributor>
				<SequenceNumber>1</SequenceNumber>
				<ContributorRole>A01</ContributorRole>
				<PersonName>Jane Smith</PersonName>
			</Contributor>
			<Language>
				<LanguageRole>01</LanguageRole>
				<LanguageCode>eng</LanguageCode>
			</Language>
			<Extent>
				<ExtentType>10</ExtentType>
				<ExtentValue>512</ExtentValue>
				<ExtentUnit>03</ExtentUnit>
			</Extent>
			<Subject>
				<MainSubject/>
				<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>
				<SubjectCode>LIT014000</SubjectCode>
				</Subject>
        ...

### Subtitles for video:

<subtitle version="1">
  <name>SampleSubtitles</name>
  <rate>24</rate>
  <resolution>
    <width>1920</width>
    <height>1080</height>
    <depth>8</depth>
    <aspect>1.778</aspect>
    <scanformat>default</scanformat>
  </resolution>
  <timecode>
    <start>01:00:00;00</start>
    <end>01:00:08;00</end>
  </timecode>
  <video>
    <title>
      <start>01:00:01;00</start>
      <end>01:00:02;00</end>
      <text>This is a subtitle string</text>
      <vertical>0</vertical>
      <horizontal>0</horizontal>
    </title>
    <title>
      <start>01:00:03;00</start>
      <end>01:00:04;00</end>
      <text>This is another subtitle string</text>
      <vertical>100</vertical>
      <horizontal>100</horizontal>
    </title>
    <title>
      <start>01:00:05;00</start>
      <end>01:00:06;02</end>
      <text>This is a third subtitle string</text>
      <vertical>-100</vertical>
      <horizontal>-200</horizontal>
    </title>
  </video>
</subtitle>

### MathML:

  <math xmlns="http://www.w3.org/1998/Math/MathML">
  	<mi>a</mi>
  	<msup>
  		<mi>x</mi>
  		<mn>2</mn>
  	</msup>
  	<mo>+</mo>
  	<mi>b</mi>
  	<mi>x</mi>
  	<mo>+</mo>
  	<mi>c</mi>
  </math>


### MusicXML: 

<score-partwise version="4.0">
  <part-list>
    <score-part id="P1">
      <part-name>Music</part-name>
    </score-part>
  </part-list>
  <part id="P1">
    <measure number="1">
      <attributes>
        <divisions>1</divisions>
        <key>
          <fifths>0</fifths>
        </key>
        <time>
          <beats>4</beats>
          <beat-type>4</beat-type>
        </time>
        <clef>
          <sign>G</sign>
          <line>2</line>
        </clef>
      </attributes>
      <note>
        <pitch>
          <step>C</step>
          <octave>4</octave>
        </pitch>
        <duration>4</duration>
        <type>whole</type>
      </note>
    </measure>
  </part>
</score-partwise>

'''

## Formatting

Back to text for publishing... the XML only tells us is what is *in* the text -- its structures and parts -- but we can use those structures as hooks for formatting rules.

A **stylesheet** defines formatting rules for named structures in the text. This works in Microsoft Word, in Adobe InDesign, in your web page, and in XML more generally. 

We define rules that say things like: body copy should be 10pt Garamond on 14pt line spacing, with a 56 em line length. First-level heads should be 18pt Gill Sans -- unless they appear in the context of a sidebar, in which case it should be 12pt instead. 

A stylesheet like this produces a "templated" design -- as opposed to being hand-crafted or bespoke. The power of a templated design is that the same stylesheet can be applied to many documents. It also means that one stylesheet can be swapped for another -- changing the formatting of a document without changing the text itself. Such an approach may be useful in the context of accessibility, or in multi-mode delivery.

This formal separation of the text (and its named structures) and the formatting rules is one example of the concept of "separation of concerns," which is a more general design pattern. We have had separation of concerns in publishing since Gutenberg put moveable type into practice, and the abstract idea of a text -- in the form of a **marked up** manuscript that compositors would use in typesetting -- came to drive formatting. 

This separation of the *platonic* ideal of the text from any particular printed instance of it has both delighted and vexed scholars and critics ever since. At this very point, when the text becomes *abstract and mutable*, it also becomes capable of *fixity and durability* over centuries owing to its production and distribution in mass quantities.

## Markup and markdown

In the early 2000s, when blogging was in its early heyday, various people tried to build systems that allowed bloggers to *simply write*, without having to worry about HTML markup -- back in those days, most websites were built by hand-coding HTML. 

There were a number of similar approaches, but one that seems to have won out is **markdown**, developed by John Gruber and Aaron Swartz. Markdown was designed as a super lightweight form of markup, where minimal markup cues are embedded as punctuation. Markdown, while visually minimal, is explicit and complete enough to be *unambiguously* transformed into HTML by a simple software routine. That means that markdown is an alternative form of markup that *does that same work* as HTML.

Markdown caught on, and became embedded in lots of different web publishing systems. A host of software tools were developed to support it, and to allow writing, editing, previewing, converting, and so on. 

