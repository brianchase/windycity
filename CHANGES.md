# Release Notes

Versions of Windy City are indicated by release date. The most recent
date below is the current version, which is available on
[CTAN](https://www.ctan.org/pkg/windycity "CTAN"). Changes since then,
if any, are listed below under "Latest" and indicate updates to [Windy
City's repository](https://github.com/brianchase/windycity "GitHub:
brianchase/windycity") on [GitHub](https://github.com "GitHub").

## Latest

* fixed a bug that could prevent names in the 'editora' field from
  printing in the author's position

## 2019-02-21

* fixed reviews with titles
* in reference lists, fixed 'year' printing with 'season' or 'issue'
* much improved format of unsigned reviews in bibliographies and
  reference lists, in part restoring previous work set aside
* extended 'swapvol' option to work with 'letter', 'incollection',
  'inbook', and 'bookinbook' entries that are cross-referenced to
  entries that work with 'swapvol' (in effect, you can use 'swapvol' not
  only with volumes in collections but with works in those volumes, such
  as chapters and articles)
* improved handling of editors and translators, including support for
  translators of a 'maintitle'
* added 'library' entry and preamble options to support the 'library'
  field
* extended 'swapauth' to work with 'mvbook' and 'mvcollection' entries
* added support for \iffieldbibstring in processing 'edition' and
  'type' fields
* other bug fixes

## 2019-01-31

* added limited support for citing web pages and social media content
* added 'listvols' entry option (see documentation)
* added 'skipdate' entry option (see documentation)
* significant changes for tighter control of punctuation, among
  other things fixing the previous use of 'postpunct'
* fixed printing of publication dates for some reports
* fixed 'nameaddon' not printing after a 3-em dash in bibliographies
  (presumably, screen names should also print in this context; they do
  now)
* fixed a show-stopping bug in reference lists caused by the
  previous fix to 'nameaddon'
* fixed reprints, cross-referencing in reference lists
* other bug fixes

## 2019-01-18

* reversed default for collections, printing information for volumes
  first; the option to reverse this is called 'swapvol'
* changed option name 'transfirst' to 'swaptrans'
* fixed punctuation before 'postnote' of articles and reviews (ugh!)
* changed processing of spacing and punctuation around 'postnote' for
  all citations
* added support for swapping the place of an author with an editor or
  translator, as in CMOS 14.104
* extended the previous to cover a similar case in CMOS 14.122
* improved handling of name lists and cross-referencing
* removed no longer maintained citation commands
* other bug fixes and housekeeping

## 2019-01-07

* major additions and changes for processing collections
* fixed \parencite for unsigned articles
* fixed \parencite for cross-referencing
* fixed formatting of reviews
* added support for 'autopunct' option and 'postpunct' field for
  better handling of punctuation after citation commands (e.g.
  '\cite{something}' will end with a period, while '\cite{something};'
  will end with a semicolon)
* in light of the previous, changed \reprint command
* added support for 'shortjournal' field for parenthetical citations
* simplified 'parencite' and related macros
* improved handling of 'year', 'endyear', 'bookyear', and
  'endbookyear' fields, ensuring that the publication date of the last
  mentioned work gets printed in bibliographies and reference lists
* many bug fixes

## 2018-12-09

* simpler processing of author's position
* added support for common reference works, such as dictionaries and
  encyclopedias
* fixed \defbibcheck for reference works
* fixed short option printing urls and related data on first citations
* some fixes, though incomplete, for reviews
* other fixes for spacing and punctuation

## 2018-12-05

* added much better support for cross-referencing collections in notes
  and bibliographies, including enhanced support for treating multivolume
  collections as a single work
* support for short format of citations, with 'short' and 'ibid'
  preamble options
* added support for self-published books
* added support for electronic article IDs
* added support for 'shortauthor' namelist
* better processing of reviews, though still limited
* fixed and improved multicite output
* undid change to 'noauth' entry option (it was right the first time!)
* many bug fixes (mainly spacing, punctuation, and toggles)
* new documentation

## 2018-11-26

* fixed 'noauth' entry option (it should only affect notes)
* fixed 'inst+loc+date'
* following CMOS, made 'cite:short' print just a work's title without
  the name of the collection
* fixed name formatting for affixes like 'Jr.' in notes (no comma
  before them, unlike in bibliographies, where names are inverted)
* limited support for copublication
* limited support for publication times
* added '\footcite*' command and updated documentation

## 2018-11-23

* improved and in some cases fixed processing of numbers,
  dates, and issues of periodicals
* much better support for unsigned articles
* fixed 'type' field format
* fixed double printing of year for theses and dissertations in
  the author-date system
* fixed punctuation after 'Special issue' in bibliographies
* fixed obscure punctuation issue with *notewrapper commands
* added support for shorthandintro and improved handling of shorthands
* updated field format for DOIs
* update name formatting for affixes like 'Jr.'

## 2018-11-17

* replaced \ifthenelse with commands from etoolbox
* better handling of editors for a series, maintitle, or issuetitle
* limited support for 'endmonth' field for periodicals
* fixed extra space from multicitedelim

## 2018-11-14

* finally got a handle on the author-date format for periodicals,
  rolling back some recent changes (ugh!)
* put back preamble options 'useeditor' and 'usetranslator', which
  are necessary after all (double ugh!)
* more readable and arguably simpler date processing for periodicals
* added preamble option 'ibid' to prepare for the 17th edition of CMOS
* updated windycity.tex to reflect the last point, also to make use of
  optionlist
* remove unused entries from windycity.bib for the 15th edition of
  CMOS

## 2018-11-13

* fixed spacing of date for periodicals (resulting from recent support
  for endday field)
* fixed spacing between volumes and pages in author-date system for
  periodicals
* support names of anonymous authors as in CMOS 14.80 (16th edition)
  and CMOS 14.79 (17th edition)

## 2018-11-09

* for articles etc., limited support for 'season' field
* limited support for 'endyear' and 'endorigyear' fields
* removed unused preamble options and commented code
* fix 'inreference' bibliography alias

## 2018-11-02

* fixed author-date system printing the year of many articles twice
* fixed author-date system printing the year between an author's name
  and the field 'nameaddon'
* fixed bibliography driver for shorthands that caused it to print
  just titles, rather than full entries
* added support for 'endday' field
* 'addendum' field prints only in bibliographies and reference
  lists, not in notes
* set 'parentracker' bibliography option
* set minxrefs preamble option
* 'collsonly' preamble option sets 'minxrefs=1'
* changed 'pagetracker' bibliography option from 'true' to 'page'
* edits and fixes to windycity.sty and windycity.tex

## 2018-10-20

* fixed broken date formatting in author-date citations
* changed \DeclareSortingScheme to \DeclareSortingTemplate
* changed preamble option 'labeldate' to 'labeldateparts'
* changed special field 'extrayear' to 'extradate'
* bumped minimum compatible release to biblatex 3.8
* other minor changes for the version bump

## 2015-12-28

* added missing \setunit for when bybookauthor prints an author's name
  and the collection has an editor, translator, or compiler

## 2015-07-08

* removed an unused bibmacro
* minor edits and fixes to windycity.sty and windycity.tex
* minor edits to readme
* removed an empty line from windycity.bib
* changed the version number format to match the release date

## 2014-03-21

* improved and fixed cross-referencing of collections to other collections
* fixed missing publication year in notes under option 'reflist'
* fixed incorrect printing of 'volumes' under option 'reflist'
* minor fixes
* updated documentation

## 2014-03-02

* greatly simplified the handling of editors and translators
* changes and fixes to 'incollections', 'ed+vol+part+etc', and
  associated macros, especially affecting the placement of a book's
  series in relation to other elements
* added and changed placement of 'note' for some entry types
* added support for abstracts (via 'note' for @article)
* simplified 'reviews'
* made @unpublished an alias of @thesis
* other minor changes and fixes
* updated windycity.tex and windycity.bib

## 2014-02-26

* initial release

