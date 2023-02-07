# Key Elements of PUB 607

PUB607 is the *Publishing Technology Project* course, in which students gain *hands-on experience* with digital technologies. In Spring 2022 the course was run as a pair of smaller projects. Out of a possible six projects, each student did **two 3-week projects**. This structure became more fluid as time went on. 

This course allowed MPub students to: 

-   dig deep into some specifics of digital tech
-   gain experience with *documentation-driven project
    management*;
-   gain experience working on a decent-sized, structured IT project
    full of the kind of *ambiguities and unknowns* that typically
    characterize such projects;
-   *experiment with new technologies* without serious (business)
    consequences.

The backbone of PUB 607 is documentation. We began with goals and ideas and ended with a report on achievements and learning outcomes. This strategy gave students the means of:

- organizing priorities
- keeping colleagues informed of new developments
- keeping a record of decisions and rationales
- providing a means of evaluating achievements

The project was self-directed, with weekly meetings and occasional check-ins. Students could work solo, in pairs, or in small groups, with this printed book being the final outcome. 


### Documentation
This is the key to this project. We used the Gitit wiki to document everything. Notes, goals, questions, answers, logs, tests, results, reports. Everything. ALL YOUR DOCS ARE BELONG TO US. Make lots of pages. Define goals and scope. Research and define specific objectives. Design, build, document. 


### What is a Wiki, Anyway?

A wiki is the *simplest-possible* collaborative website -- is a tremendously powerful tool for information management. Because it is very simple, it resists complexity on the technical level. But it can be as complex -- and as messy or organized -- as you like on an editorial level. A wiki's basic structure means that almost anything that needs to be done in terms of "system administration" is in fact an *editorial* task.


*Some technical details that you don't need to know but this is Tech Class so John wrote them up for us*

There are many versions of wiki software. The most popular one out there is called MediaWiki, and it's the software that runs Wikipedia. The one we're using is called Gitit, and it's a simpler, lighter tool that has a couple of very clever features.

Gitit wiki is composed of three layers:

 - **A git repository**. Git is a file-management and version-control system used by software developers. It gives you fine precision control over a set of files being accessed by a whole bunch of people at the same time, doing a really good job of making sure everyone has the latest version of everything and sorting out editing conflicts. A git repository (or "repo") is really just a folder full of text files with some magical version-control stuff going on behind the scenes. A git repository can be copied into multiple locations (your computer, my computer, a webserver) and the git software will keep all changes strictly synchronized across all locations.

 - **Pandoc** is the universal file-conversion tool I was evangelizing when we talked about single-source publishing earlier this year -- and upon which one of the Projects is based. Pandoc isn't doing much in our wiki -- just converting between markdown and the formatted HTML you see on the pages -- but it's a nice standard tool in that capacity.

3) a webserver layer that makes the above two layers into a nice navigable website.

Gitit is running (on port 8000) on press.ccsp.sfu.ca which is actually the iMac on the desk in my office. Gitit is open-source software, and while it takes a bit to install it (it relies on layers and layers of software development tools), it's pretty much dead simple after you've sat through the installation screens. 

Because the back end of the wiki is a git repository -- where each 'page' is just a text file -- you can clone the whole thing to another computer. You could edit these files remotely, and send them back into the wiki. You could access all these pages and turn them into an ebook. Actually, that's a pretty good idea...


### The Projects
**Ebooks with InDesign**

Start with a 'manuscript.' Project Gutenberg, or whatever. Load it into InDesign, format as needed, then export as EPub3. Test. Fix. Repeat. Can it be better? Do it again...

**Ebooks with Pandoc**

Start with a 'manuscript.' Project Gutenberg, or whatever. Format it in markdown. Run it through Pandoc. Test. Fix. Repeat. Can it be better? Do it again...

**Audio for podcasting**

Define the podcast. Plan and 'script' two episodes. Plan recording. Get equipment. Workshop with Hannah on the recording. Record. Re-record. Repeat. Edit. Make plans for distribution.

**Audio for audiobooks**

Start with a 'manuscript.' Project Gutenberg, or whatever. Edit to suit. Get your 'voice talent' cued up. Workshop with Hannah on the recording. Record. Re-record. Repeat. Edit. Make plans for distribution.

**APIs and Biblioshare**

Start with Biblioshare API and experiment with all the things you can get out of it -- ONIX and otherwise. I will provide a list of ISBNs from the Alcuin Design awards. THEN, read the lovely Totoro tutorial, and see if you can create a computer program that gets data from the API and turns it into a catalog, or something similarly useful.


**Accessibility Tech**

Define your scenario(s). Identify the challenges and possible solutions. Research possible tools to help reach solutions. Prototype a demo. Test. Repeat.