pandoc-thesis-template

A template for creating a degree project thesis in markdown + pandoc

##Installing

*   You need Pandoc and LaTeX installed.

**Pandoc installation**

NOTE (Feb 2017): A couple of my students with Windows 10 had issues installing the latest version of Pandoc. But it all works fine with version 1.91.1. So if you had an issue, then try installing that version from the 'releases' download page

I also recommend installing Composer, to save pasting that long command at the command line (or make or whatever you prefer ...)

**Composer installation**

Running

If you have Composer installed just type:

    $ composer pdf
    
If you prefer JSON format for your list of reference items, the type:

    $ composer json
    
The only difference between these two Composer scripts (look inside composer.json) is the bit about references:

    --bibliography=05_references/references.bib
    
If not you need to enter the following at the command line:

    pandoc --latex-engine=xelatex -H preamble.tex -V fontsize=10pt -V documentclass:book -V papersize:a4paper -V classoption:openright --number-sections --bibliography=99_references/references.bib --csl='csl/nature.csl' 00_front_material/1_title.md 00_front_material/2_declaration.md 00_front_material/3_abstract.md 00_front_material/4_acknowledgements.md 05_toc/toc.md 10_chapters/chapter1_introduction/introduction.md 10_chapters/chapter1_introduction/introduction_section2.md 10_chapters/chapter3_extra_results.md 10_chapters/chapter4_generaldiscussion.md 88_appendices/a_meetings/meetings.md 99_references/references.md -o _THESIS.pdf

If you add a chapter or appendix, then add its name (in the appropriate place in the sequence, e.g. chapter 4 after chapter 3) in the command. That's it!

**References**

The collection of references are in 
    
    /99_references/references.bib

Only items that are cited will be added to the list of refernces in the generated PDF.

**Citations**

To cite a reference item write the 'id' of the reference item in square brackets with an '@-at' sign as follows:

Lots of people have written about how wonderful Pandoc is, for example see [@smith2017].
where in the above smith2017 is the unique 'id' of the reference item. This would output something like this (if citations mode is Harvard):