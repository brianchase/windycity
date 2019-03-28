# Windy City

## About

Windy City is a style for [biblatex](http://www.ctan.org/pkg/biblatex
"biblatex") that formats notes, bibliographies, parenthetical
citations, and reference lists according to the 17th edition of [The
Chicago Manual of Style](http://www.chicagomanualofstyle.org/ "Chicago
Manual of Style"). It accurately handles a wide range of citations and
includes a set of options and commands to support special
circumstances. It also has extensive support for citing and arranging
different kinds of editors, translators, and compilers within a single
citation. These features make Windy City especially suitable for
academic work.

Windy City's latest release is available on
[CTAN](https://www.ctan.org/pkg/windycity "CTAN: pkg/windycity"), the
[Comprehensive TeX Archive Network](https://www.ctan.org "CTAN"). It
includes a PDF of the [user
guide](http://mirrors.ctan.org/macros/latex/contrib/biblatex-contrib/windycity/doc/windycity.pdf
"windycity.pdf"). More recent changes are available at Windy City's
[repository on GitHub](https://github.com/brianchase/windycity
"GitHub: brianchase/windycity").

## Getting Started

If you already know how to use
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex"), getting
started with Windy City is easy. The first task is to confirm that
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex") and Windy City
are installed properly on your system. Since both are included in some
distributions of [LaTeX](https://en.wikipedia.org/wiki/LaTeX "LaTeX"),
you might be able to skip this step.

Windy City consists of four files:

* [windycity.dbx](https://github.com/brianchase/windycity/blob/master/windycity.dbx "windycity.dbx")
* [windycity.bbx](https://github.com/brianchase/windycity/blob/master/bbx/windycity.bbx "windycity.bbx")
* [windycity.cbx](https://github.com/brianchase/windycity/blob/master/cbx/windycity.cbx "windycity.cbx")
* [american-windycity.lbx](https://github.com/brianchase/windycity/blob/master/lbx/american-windycity.lbx "american-windycity.lbx")

If you need to install Windy City on your system, you may copy its
files to one of several places. One option is to locate
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex") on your system
and use its directories:

* .../biblatex/[windycity.dbx](https://github.com/brianchase/windycity/blob/master/windycity.dbx "windycity.dbx")
* .../biblatex/bbx/[windycity.bbx](https://github.com/brianchase/windycity/blob/master/bbx/windycity.bbx "windycity.bbx")
* .../biblatex/cbx/[windycity.cbx](https://github.com/brianchase/windycity/blob/master/cbx/windycity.cbx "windycity.cbx")
* .../biblatex/lbx/[american-windycity.lbx](https://github.com/brianchase/windycity/blob/master/lbx/american-windycity.lbx "american-windycity.lbx")

If you prefer not to mix Windy City's files with
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex")'s, another
option is to find where your distribution of
[LaTeX](https://en.wikipedia.org/wiki/LaTeX "LaTeX") keeps
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex")'s third-party
style files and proceed accordingly. Yet another option is to install
Windy City in your local `texmf`. Its location will depend on your
system and preferences. For a one-off compilation, say, to give Windy
City a trial run on a single document, you can copy Windy City's files
to the document's root directory.

After copying the files to one of those places — or another of your
choosing — remember that for every option but the last (a document's
root directory), you need to update your `texmf` file name database.

To compile a document with Windy City, tell
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex") to load it
with the load-time option `style`:

```
\usepackage[style=windycity]{biblatex}
```

Typically, this goes in a document's preamble or in one of its style
files.

For some entries in your bibliography database, you may need to add
fields or make other adjustments to get the right output. But since
Windy City relies as much as possible on standard
[BibTeX](http://www.bibtex.org "BibTeX") fields, and secondarily on
[biblatex](http://www.ctan.org/pkg/biblatex "biblatex") fields, you
may not need to make major changes. The examples in this document and
its accompanying bibliography database,
[windycity.bib](https://github.com/brianchase/windycity/blob/master/doc/windycity.bib
"windycity.bib"), should serve as a guide for how to manage your input
for nearly every circumstance that the style is meant to handle.

## License

Copyright (c) 2019 Brian Michael Chase. Under the terms of the [LaTeX
Project Public License](http://www.latex-project.org/lppl.txt
"lppl.txt"), version 1.3, permission is granted to copy, distribute,
or modify this software. See also
<https://www.latex-project.org/lppl/>.

This software is provided as is, without warranty of any kind, either
expressed or implied, including, but not limited to, the implied
warranties of merchantability and fitness for a particular purpose.

## Requirements

* [biblatex](http://www.ctan.org/pkg/biblatex "biblatex") 3.8 or higher

