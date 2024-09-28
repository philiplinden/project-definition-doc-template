# Getting started in LaTeX

## What are all these files?

LaTeX uses several different types of files to generate a beautiful looking document.

* `.tex` _("tech" file)_ This is the heart of your paper. All content, titles, sections, and tables live here.
* `.cls` _("class" file)_ These are the formatting rules LaTeX uses to place text and choose fonts, et cetera. Normally, this file will not need to be changed. If it ain't broke, don't fix it!
* `.bib` of `.bibtex` _("bib tech" file)_ This is a configuration file that contains all the information used to generate your references and bibliography. You define a reference type and define keywords that contain the reference's information. Most scientific and technical papers provide citations in BibTeX formats. Use [BibMe](http://www.bibme.org/bibtex) to automatically generate BibTeX code for your references. A complete list of BibTeX types and examples of their uses can be found [here](https://verbosus.com/bibtex-style-examples.html).
* LaTeX generates a number of other temporary files when it converts your `.TeX` file into a `.PDF` document. If you are using the Atom text editor on Windows, you can clear these files with the shortcut `ctrl+alt+c` (this shortcut may be found and changed in the settings of the `latex` Atom package).

## Where do I start?

1. [Download the template!](https://github.com/RIT-Space-Exploration/SPEX-Standard-Proposal/releases)
2. Open the `.tex` file. Read the comments!
3. Replace the sample content with your own.
4. Compile the document (`ctrl+alt+b`)
5. Rinse and repeat.

## I don't have LaTeX on my computer. Can I still work on my documents?

Yes! Don't forget that you can edit LaTeX code in any text editor. To see the beautiful typeset results of all your coding, you have a few options:

* Install a LaTeX compiler on your computer. ([There's a tutorial for that here.](Setting-up-your-computer-to-work-with-LaTeX))
* Render the code online. [ShareLaTeX](https://www.sharelatex.com/) and [Overleaf](https://www.overleaf.com/) are online tools where you can render your LaTeX code in your web browser.

__Phil's opinion:__ As great as it may seem to edit your code in your browser and even use WYSIWYG (What You See Is What You Get) formatting, like Word, it quickly becomes a crutch. Editing code on your own machine and using a git repository to track changes and collaborate is by far a more robust approach to developing LaTeX documents.

## What are LaTeX packages?

LaTeX is extensible. This means that additional functionality, shortcuts, functions, and more can be added to the base capability of LaTeX through code _packages_ that are loaded in at the top of your document.

At the beginning of your `.tex` file, you should have something like this:

```tex
\documentclass[journal]{IEEEtran}
\usepackage{graphicx}
\usepackage{cite}
\usepackage{multirow}
\usepackage[flushleft]{threeparttable}
\usepackage{booktabs}
\usepackage{siunitx}
\usepackage[T1]{fontenc}
\usepackage[pdftex,breaklinks,pdfauthor={MSD Team P17101},pdfcreator={Philip Linden},pdftitle={P17101 Arcjet Thruster}]{hyperref}
\usepackage{nomencl}
```

|  | Phil's favorite packages |
| --- | --- |
| `graphicx` | Insert and format figures. |
| `cite` | Citations and footnotes. |
| `siunitx` | Easy units formatting. |
| `hyperref` | Reference URLs, footnotes, and more. Automatically injects internal links between footnotes and their references when opening a PDF in Acrobat. |
| `booktabs` | Make beautiful tables. Be mindful of how you style tables! Use these guides: [GUIDE 1](https://www.inf.ethz.ch/personal/markusp/teaching/guides/guide-tables.pdf) [GUIDE 2](http://cs.brown.edu/about/system/managed/latex/doc/booktabs.pdf)

## What is BibTeX?

When you cite references, these citations point to entries of your bibliography. A Bib file (`.bib`) contains all the information belonging to each of your references, including reference type, year, author, title, and even URL. BibTeX is the syntax used to organize all this information.

Many publications provide a citation in BibTeX format, and [Google Scholar](https://scholar.google.com/) automatically generates BibTeX citations for some publications, too.

BibTeX citations can be searched and even created at <http://www.bibme.org/bibtex>

[Here's a detailed guide on formatting BibTeX.](https://www.economics.utoronto.ca/osborne/latex/BIBTEX.HTM)

At the end of your `.tex` document, you should have something like this:

```tex
\bibliographystyle{IEEEtran}
\bibliography{p17101}
```

Where, in this case, my document `p17101.tex` references my bibliography file `p17101.bib`
