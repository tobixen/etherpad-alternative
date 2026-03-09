This describes a possible future project.  Research should exist to see if there are any existing solutions that could fit the bill, or if it's possible to simply build on top of the existing etherpad service.

## What do we want

Something like Etherpad, just better.  An open-source web service that easily can be spun up on any server, ad-hoc or permanently.

It may be a bit more async than Etherpad.  Etherpad is great for interactively and collaborately creating some draft of a document over a beer.  I've also seen it used for participants of a video meeting creating notes from the meeting while it's going on.  For such purposes one should rather use Etherpad. This service should be the ultimate tool for tweaking a document over some days or weeks and produce some text that all the authors can readily sign

Scalability is not an important requirement.  It's meant for collaboration for a group, not for a hosting a public wikipedia-clone or as the primary document editing tool for a megacorporation.

Authentication and authorization is outside the scope (secret URLs and/or a web server in front can take care of that).

An embedded document-wide chat is outside the scope - in most usage cases, the participants are already connected through some other chat system, a chat service embedded in the document creates a risk of scattering the communication.  However, the possibilities to comment on code lines may be important.

## Target audience

* Primarily technically minded people, wanting to edit git-backed text files, including markdown, program code, yaml and whatnot.
* Secondarily Non-technical people wanting to edit some simple text

## Annoyances with Etherpad

* Antifeature: Etherpad is not designed to edit plain text files.  It has possibilities to add bold text, ordered lists, etc.  I consider this to be anti-features - if anyone uses those features, it gets difficult to export the document. The standard text file export will drop information.
* Version control and visibility: Who changed what and when?  What changes have been made to the document since my last visit?  Etherpad has all the information, but no good interface to access it.  Given that the target audience here is technically-minded people, having the file git-backed will solve this problem very easily.
* Annotations: Etherpad has a document-wide chat, but it's missing the possibility to attach comments and discussions to text lines.  It's a requirement that those comments are stored inside the git repository, this will be a bit techically challenging.

## Nice-to-have features

* Git export functionallity - possibility for clients to point their git to the server.  (We should not reinvent the wheel here - use existing libraries or software components for it).
* "Preview" formatting of markdown-files.  Markdown has become the de-facto standard for enriched text.  (Again, important not to reinvent the wheel, but reuse existing libraries).
* Fruit-salad mode with color-coding of well-known file types / programming languages, etc (both for the whole document, and for backticked code sections in a markdown file)
* WYSIWYG-editing of markdown text.  Personally I think it's an anti-feature, but the not-so-technically-minded may like it.
* Export to PDF.  Again, there exists many libraries for this.
* Nifty user interfaces for checking "activity since my last visit" and things like that, for people who are not familiar with git.

## TODO

* Clean up typos and bad grammar in this document
* Do research on existing solutions.  (Does gitea allow collaborative editing of documents?)
* If nothing suitable found, make a design for a python-based service (we're primarily python programmers, after all).

(Those points can easily be done by AI, but I've burned my weekly quota at Claude)
