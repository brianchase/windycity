# Windy City

## About

Windy City is a style for [biblatex](http://www.ctan.org/pkg/biblatex)
that formats notes, bibliographies, parenthetical citations, and
reference lists according to the 17th edition of [The Chicago Manual
of Style](http://www.chicagomanualofstyle.org/home.html). It
accurately handles a wide range of citations and includes a set of
options and commands to support special circumstances. It also has
extensive support for citing and arranging different kinds of editors,
translators, and compilers within a single citation. These features
make Windy City especially suitable for academic work.

For more information, please see Windy City's
[documentation](https://s3.amazonaws.com/brianchase/windycity.pdf
"windycity.pdf") (PDF) or [click
here](https://s3.amazonaws.com/brianchase/windycity.zip
"windycity.zip") (ZIP) to download the complete package.

## Getting Started

If you already know how to use
[biblatex](http://www.ctan.org/pkg/biblatex), getting started with
Windy City is easy. Locate
[biblatex](http://www.ctan.org/pkg/biblatex) on your system, and copy
Windy City's files into their respective directories:

* .../biblatex/[windycity.dbx](https://github.com/brianchase/windycity/blob/master/windycity.dbx)
* .../biblatex/bbx/[windycity.bbx](https://github.com/brianchase/windycity/blob/master/bbx/windycity.bbx)
* .../biblatex/cbx/[windycity.cbx](https://github.com/brianchase/windycity/blob/master/cbx/windycity.cbx)
* .../biblatex/lbx/[american-windycity.lbx](https://github.com/brianchase/windycity/blob/master/lbx/american-windycity.lbx)

Next, tell [biblatex](http://www.ctan.org/pkg/biblatex) to load Windy
City with the load-time option `style`:

```
\usepackage[style=windycity]{biblatex}
```

For some entries in your bibliography database, you may need to add
fields or make other adjustments to get the right output. However,
since Windy City relies as much as possible on standard BibTeX fields,
and secondarily on [biblatex](http://www.ctan.org/pkg/biblatex)
fields, you may not need to make major changes. The examples in this
document and its accompanying bibliography database,
[windycity.bib](https://github.com/brianchase/windycity/blob/master/doc/windycity.bib),
should serve as a guide for how to manage your input for nearly every
circumstance that the style is meant to handle.

## License

Copyright (c) 2019 Brian Michael Chase. Under the terms of the [LaTeX
Project Public License](http://www.latex-project.org/lppl.txt),
version 1.3, permission is granted to copy, distribute, or modify this
software.

This software is provided as is, without warranty of any kind, either
expressed or implied, including, but not limited to, the implied
warranties of merchantability and fitness for a particular purpose.

## Requirements

* [TeX Live](http://www.tug.org/texlive "TeX Live")
* [biblatex](http://www.ctan.org/pkg/biblatex "biblatex") 3.8 or higher

