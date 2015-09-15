# Thesis for osm2vectortiles

This is the thesis associated with the
[geometalab/osm2vectortiles](https://github.com/geometalab/osm2vectortiles) project.
The project contains issues regarding the documentation and other tasks
that don't belong to the project repository.

The thesis is written in Markdown based on the
[tompollard/phd_thesis_markdown](https://github.com/tompollard/phd_thesis_markdown) template.

## Why is the thesis written in Markdown?

The plain text format is easy to work with and allows us to convert it to a bunch
of other formats.

A more exhaustive list of reasons can be found [here](https://github.com/tompollard/phd_thesis_markdown#why-write-my-thesis-in-markdown).

## Setup

### How is the template organized?

- README.md => these instructions.
- LICENSE => terms of reuse (MIT license).
- Makefile => contains instructions for using Pandoc to produce the final thesis.
- source/ => directory to hold the thesis content. Includes the references.bib file.
- source/figures/ => directory to hold the figures.
- style/ => directory to hold the style documents.

### How do I get started?

1. Install the following software:
    - A text editor, like [Sublime](https://www.sublimetext.com/), which is what you'll use write the thesis. 
    - A LaTex distribution (for example, [MacTex](https://tug.org/mactex/) for Mac users).
    - Set the PATH variable to the directory where MacTex is installed `export PATH=/usr/local/texlive/2015/bin/x86_64-darwin:$PATH`
    - [Pandoc](http://johnmacfarlane.net/pandoc), for converting the Markdown to the output format of your choice.  You may also need to install [Pandoc cite-proc](http://pandoc.org/demo/example19/Extension-citations.html) to create the bibliography.
    - Git, for version control.
2. [Fork the repository](https://github.com/tompollard/phd_thesis_markdown/fork) on Github  
3. Clone the repository onto your local computer (or [download the Zip file](https://github.com/tompollard/phd_thesis_markdown/archive/master.zip)).  
4. Navigate to the directory that contains the Makefile and type `make pdf` (or `make html`) at the command line to update the PDF (or HTML) in the output directory.
5. Edit the files in the 'source' directory, then goto step 4.
6. Type `grunt watch` to automatically compile changes.

### What else do I need to know?

Some useful points, in a random order:
- each chapter must finish with at least one blank line, otherwise the header of the following chapter may not be picked up.
- add two spaces at the end of a line to force a line break.
- the template uses [John Macfarlane's Pandoc](http://johnmacfarlane.net/pandoc/README.html) to generate the output documents. Refer to this page for Markdown formatting guidelines.
- PDFs are generated using the Latex templates in the style directory. Fonts etc can be changed in the tex templates.
- To change the citation style, just overwrite ref_format.csl with the new style. Style files can be obtained from [citationstyles.org/](http://citationstyles.org/)
- For fellow web developers, there is a Grunt task file (Gruntfile.js) which can be used to 'watch' the markdown files. By running `$ npm install` and then `$ npm run watch` the PDF and HTML export is done automatically when saving a Markdown file.
- You can automatically reload the HTML page on your browser using LiveReload with the command `$ npm run livereload`. The HTML page will automatically reload when saving a Markdown file after the export is done.
