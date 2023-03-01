## Examples of Markup Languages

The original markup language standards SGML, HTML, and early XML) were designed for publishing; they were concerned with marking up texts for processing, printing, searching, and distribution online. But the "generalized" or "extensible" idea (the G in SGML; the X in XML) means these ways of treating text become useful as notation systems to describe data.


### HTML -- that is, prose text for publishing, in a website, in an ebook, etc.:

```
<html>
  <body>
    <section id="pub-607-fundamentals" class="level1">
      <h1>PUB 607 Fundamentals</h1>
      <section id="on-file-management" class="level2">
        <h2>On File Management</h2>
        <p>A file is a <strong>metaphor</strong> for a structured bundle of data in a computer. Files do not actually exist in your computer, or on its hard drive (which is not in fact hard). It’s a metaphor that shapes a set of behaviours around how we deal with files. The metaphor is closely related to the idea of “documents,” but not exactly equivalent.</p>
        <p>The file idea, more or less, dates to the late 1960s, early 1970s, and was popularized through the spread of the Unix operating system (which is still with us). We still think largely in terms of files, although alternative metaphors (or patterns) are becoming more common: streams; queries; things pulled together on the fly out of databases.</p>
        ...
```

### SVG, Scalable Vector Graphics, a web-portable graphics standard [Click to see live](svg.md)

[Click to see live](svg.md)

```
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
```

### RSS, or syndication feeds for podcasts, blogs, news headlines, etc:

```
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
```

### ONIX, bibliographic data for the book supply chain

```
<ONIXMessage release="3.0">
  <Product>
    <ProductIdentifier>
      <ProductIDType>15</ProductIDType>
      <IDValue>9780999999991</IDValue>
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
```

### Subtitles for video:

```
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
```

### MathML:

```
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
```

### MusicXML:

```
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
```
