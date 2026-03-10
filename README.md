This describes a possible future project.  Research should exist to see if there are any existing solutions that could fit the bill, or if it's possible to simply build on top of the existing etherpad service.  Contributions are most welcome.

## What do I want

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
* Slightly irrelevant rant: Google Docs is the most commonly used alternative to Etherpad.  At some point they introduced the concept of pages.  In the previous millenium this may have been considered a feature as the prime purpose of editing a document often was to print out the letter.  Does Google stick to local standards or the international paper size standard?  Even in the previous millenium documents made for the wrong paper size was an anti-feature.  For editing code, this is obviously an anti-feature.

## Nice-to-have features

I think there exists libaries or software components for everything below - I think it's important not to reinvent the wheel.

* Git export functionallity - possibility for clients to point their git to the server.
* "Preview" formatting of markdown-files.  Markdown has become the de-facto standard for enriched text.
* Fruit-salad mode with color-coding of well-known file types / programming languages, etc (both for the whole document, and for backticked code sections in a markdown file)
* WYSIWYG-editing of markdown text.  Personally I think it's an anti-feature, but the not-so-technically-minded may like it.
* Export to PDF.
* Nifty user interfaces for checking "activity since my last visit" and things like that, for people who are not familiar with git.
* Federation - should be easy to clone the git-repo locally, spin up a local web service and automatically have the git repos synced

## Tehcnical challenges

* Storing comments on the produced text while keeping it git-backed.  Suggestion: embed the comments in the file itself, but in a different branch.
* Conflict resolution.  Short-term workaround: throw a red text at the user, save the work in a separate branch and have the user manually resolve the conflicts

## Possible existing solution

* **Gitea** - I haven't tested it yet, but Gitea is a gitlab/github competitor, should be really easy to roll out, and offers web-interface for editing files.  It probably does not offer the possibility for interactive real-time collaboration, but perhaps an async solution would do for most purposes?  Research should be done on it.
* **NextCloud** does have the possibility for collaboratively edit markdown-text
* **YJS** - https://github.com/yjs/yjs
* Others?

## TODO

* Clean up typos and bad grammar in this document
* Do research on existing solutions.
* If nothing suitable found, make a design for a python-based service (because that's my primarily programming language nowadays ... if someone else will do the project, then some other programming language may be better).

(Those points can easily be done by AI, but I've burned my weekly quota at Claude)
