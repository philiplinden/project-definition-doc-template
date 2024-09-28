# Frequently Asked Questions

## Getting started

☕ [LaTeX Quickstart Tutorial](latex-quickstart.md)

🔥 [Begin LaTeX in minutes](https://github.com/LewisVo/Begin-Latex-in-minutes)

## Using project definition documents (PDDs)

### Who should write a PDD?

Anyone is welcome to write about a project and present it using the PDD format.
If any student, scientist, engineer, or enthusisastic individual has an idea for
a technical project, writing a PDD is a great way to document their concept,
archive it, and perhaps present it to an organization like
[MoonDAO](https://moondao.com/) for support to grow towards the next level. The
project "Champion" is the primary author of the definition document and, similar
to a Principal Investigator, leads a preliminary team in developing a project
idea. The Champion is not necessarily the project manager for a project they
propose. Faculty recommendations, advice, and support for a project is not
necessary but is strongly encouraged. The Champion is the main point of contact
for the PDD. The project's Champion be handed off over time, but a project must
always have a Champion.

### Will my PDD be rejected?

PDDs are not approved nor rejected. PDDs are archived, so a definition document
that doesn't initially take off may be picked up by a new team somewhere down
the line.

### Is my definition document binding?

In the ideal project life cycle, a PDD defines a set of objectives or
deliverables which are fulfilled and discussed in a final report or paper. In
practice, this is not always the case but an PDD should guide a project such
that "feature creep" is avoided and good science is achieved.

### Should I rewrite my PDD?

Probably not. The purpose of a design document is to capture and preserve the
essence of your original idea. In reality, ideas may grow and change over time.
If this is the case, it is better to use your old PDD as a template for a new
one than to go for a rewrite. On the other hand, it is acceptable to polish and
edit a PDD for the sake of clarity and concision, but usually this is done
before work has begun on that project. This question lies squarely in the
_spirit_ of a PDD, and is thus up to interpretation. Use your best judgement, I
trust you.

## Using the template

### Are all the sections in the template required?

Short answer: No.

Long answer: **The template was written as a functional example. Read it!** One
reason to write a PDD is to guide you to focus and refine your project concept.
Writing this document will hopefully guide you to think about how your project
will grow in the future and and what major obstacles will be in your way. While
many sections of the template are specific to the template as a PDD itself, I
expect many of the same discussions to appear in your project as well.

### The template is broken or missing something important

Create a new [issue](https://github.com/philiplinden/project-definition-doc-template/issues)
describing your problem so it can be fixed.

## Using TeX, for better and for worse

### Why use LaTeX instead of a regular word processor?

LaTeX is not a word processor. It allows you to write content without worrying
about formatting or typesetting -- LaTeX handles all the organization,
placement of text, spacing, headings, and so on. It is the de facto standard
for technical and scientific documents, and it is beneficial for you to be at
least somewhat familiar with using it, especially if you plan to do research in
the future. For more about LaTeX, [visit their homepage](https://www.latex-project.org/about/).

### But I don't know how to write LaTeX

Fear not, my apprentice. LaTeX can be tricky to work with, especially when
starting out. Lucky for you there is a vibrant TeX community on [stack
exchange](https://tex.stackexchange.com/) and across the web. I recommend new
users to modify templates, ask lots of questions, and experiment.

### My bibliography won't show up

- Make sure you've created a `.bib` file and it's properly formatted! Look to
  the [examples](examples/) or [reference](reference/) docs to steal citations
  that compile.
- Have you made any citations? Whenever you reference an external work such as
  a textbook or research paper, you must use the `\cite{your-reference}`
  command to insert a citation. No matter how many references you have in your
  `.bib` file, LaTeX only shows the ones you have cited.
- Are you telling LaTeX to make the bibliography? Insert the following commands
  after your acknowledgements and before your appendix:

```tex
\bibliographystyle{IEEEtran}
\bibliography{YOUR-BIB}
```

(in this example, I have a file called `YOUR-BIB.bib` in the same directory as
my `.TeX` file.)

### How do I make nice looking tables?

I'm so glad you asked! [Here's a great style guide to effective and beautiful LaTeX tables](https://www.inf.ethz.ch/personal/markusp/teaching/guides/guide-tables.pdf).

The package `booktabs` is highly recommended. Its usage is also described in
the style guide.

![GIF example](https://i.imgur.com/ZY8dKpA.gif)

### Why is my linter yelling at me over periods and dashes?

Because it matters!

- `-` (hyphen), `--` (en-dash) and `---` (em-dash) are actually different
  characters and have different uses.
- Hyphens (`-`) are used for word breaks and hyphenated words like
    "noise-canceling headphones." Don't worry about this one too much. LaTeX
    automatically hyphenates word breaks and there's no real "proper" rule
    for hyphenating words.
- En-dashes (`--`) are used to delineate ranges like "1991--1995" or "2--3
    weeks." Looks goofy in code, but really nice in print.
- Em-dashes (`---`) are used to place things like interjections---an
    uncommon grammar device in research papers---in among other parts of a
    sentence.
- More info: <https://tex.stackexchange.com/questions/3819/dashes-vs-vs>
- Spacing is actually handled differently with periods that appear between
  letters of an abbreviation, after a word like "etc.", or, of course, at the
  end of a sentence. There are only a couple special cases to worry about, and
  even then this is only the "proper" usage (but it's optional).
  - [READ THIS FIRST](https://tex.stackexchange.com/questions/99543/exhaustive-list-of-use-cases-for-the-interword-space).
  - Non-breaking space (`~`) - This is used when you don't want two words to
      be separated if LaTeX wants to push one of them to a new line. It will
      appear as a space in text, but `these~words` will be handled like one
      "chunk." Use this one in between first and last names, or between titles
      and names like `Dr.~John~Smith`
  - Interword space (`\`) - The Guide to LaTeX (4e) states that \␣ is a
      "[n]ormal space between words after a command without arguments or after
      a period that is not the end of a sentence" (p. 467).
  - Intersentence space (`\@`) - [Read this](https://tex.stackexchange.com/questions/55105/when-should-i-use-intersentence-spacing/55112#55112).
