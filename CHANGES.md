# Release Notes

Versions of Windy City are indicated by release date. The most recent
date below is the current version, which is available on
[CTAN](https://www.ctan.org/pkg/windycity "CTAN: pkg/windycity").
Changes since then, if any, are listed below under "Latest" and
indicate updates to Windy City's [repository on
GitHub](https://github.com/brianchase/windycity "GitHub:
brianchase/windycity").

## 2021-05-02

This release brings a long overdue redesign of the workflow for
editors and translators. My hope is that users won't need to change
their bibliography databases, but I did need to change one example in
the user guide, moving an editor name list from a child entry to its
parent, where it belonged in the first place. In all, the changes
greatly extend the control and flexibility that users have over the
placement of editors and translators while allowing for simpler
internals.

* highlights pertaining to editors and translators:

  - added support for the following editorial roles:

    + expanded by...
    + expanded and compiled by...
    + expanded and edited by...
    + expanded and revised by...
    + expanded and translated by...
    + expanded and updated by...
    + compiled and expanded by...
    + edited and expanded by...
    + revised and expanded by...
    + translated and expanded by...
    + updated and expanded by...

  - added support for translators of `issuetitle` and `series`, which
    means you may assign translators to every title to which you may
    assign editors
  - editor and translator type fields now accept comma-separated
    bibliography strings, making all editorial roles available for
    `issuetitle`, `maintitle`, and `series` (e.g. if `editor` is the
    reviser of `maintitle`, put `maintitle,reviser` or
    `reviser,maintitle` in `editortype`)
  - added `swaptrans:issuetitle`, `swaptrans:maintitle`, and
    `swaptrans:series` entry options to swap positions of editors and
    translators of `issuetitle`, `maintitle`, and `series`
  - for special circumstances (explained in the user guide), added
    three more entry options for swapping editors and translators:
    `swaptrans:title`, `swaptrans:booktitle`, and
    `swaptrans:bookbooktitle`
  - added support for printing a second tier of editors after `title`,
    `issuetitle`, `maintitle`, and `series` (e.g. "Edited by Jane Doe.
    Revised and Expanded by John Smith")
  - if the editors and translators of a work are the same, you can
    control the assignment in several ways, including with just one
    name list and its corresponding type field (e.g. if Jane Doe is
    the compiler and translator of `title`, you can, among other
    options, put `Doe, Jane` in `editor` and `comptrans` in
    `editortype` or `Doe, Jane` in `translator` and `comptrans` in
    `translatortype`)
  - fixed several issues, at least, affecting the placement of
    editors and translators, mainly the latter

* added preamble option `shortafter` to print the same output as the
  preamble option `short` but with long first citations
* for works in certain collections, fixed punctuation after the
  `edition` field

## 2021-01-30

* added support for the `pubstate` field to indicate when a work is
  forthcoming (with value *forthcoming*), a preprint (with value
  preprint*), a working paper (with value *working*), or an electronic
  article published ahead of the official publication date (with value
  *prepub*)
* added support for the `eprint` field, plus related fields and
  options
* added `shortlinks` preamble option to "shorten" embedded links from
  `bibhyperref` in standard citations; instead of encompassing an
  entire citation, links apply to just one element: the title or, if
  no title is present, whatever part of the citation occupies the
  author's position, such as the author's name, *ibid.*, or a
  shorthand
* somewhat related to the previous, changed preamble option
  `firstshort` to `shortfirst`
* sorting in bibliographies and reference lists now respond to the
  month, day, hour, and minute or entries (e.g. in a reference list,
  two articles by the same author published on the same day, minutes
  apart, will sort the earliest article first)
* added `noreprint` entry option to exclude the `reprint` bibliography
  string from citations of certain reprints
* fixed the `shortauthor` field printing in long, first citations
  (sorry about that!)
* fixed several bugs, mostly affecting parenthetical citations, having
  to do with the placement, punctuation, and tracking of citations
  with `journaltitle`, `organization`, or `blogtitle` in the author's
  position
* related to the previous, added support for the `shortjournal` field
  and added `shortorganization` and `shortblog` fields
* fixed several macros in which the preamble option `reflist` could
  cause errors in standard citations
* fixed parenthetical citations for `@online` entries that should have
  nothing in the date's position, not even "n.d." (no date), such as
  when you cite a blog but not any particular post
* fixed punctuation after `title` when an `@unpublished` entry has no
  `type`, `location`, or `pubstate` field
* [accidentally dropped from previous release:] fixed `autopunct` when
  `\footcites` follows `\cite` plus an `autopunct` mark (e.g.
  `\cite{key1}?\footcites{key2}{key3}`)

## 2020-11-10

* added support for updaters, which, like other editorial roles, you
  can combine with any other role:

  - updated by...
  - updated and compiled by...
  - updated and edited by...
  - updated and revised by...
  - updated and translated by...
  - compiled and updated by...
  - edited and updated by...
  - revised and updated by...
  - translated and updated by...

* when editors and translators are the same, and you haven't set the
  `swaptrans` entry option, the value of the `editortype` field
  determines which role goes first (example: `transrev` prints
  "translated and revised by" without needing `swaptrans`)
* dropped the `anonauth` and `anonqauth` entry options; instead, use
  the `authortype` field with values `anon` and `anon?`, respectively
* in addition to anonymous authors, `authortype` can handle some
  pseudonymous authors with the value `pseudo` (the `nameaddon` field
  still works for this and, in fact, remains the only way to list a
  pseudonymous author's given name)
* added a `nopages` bibliography option to stop automatic printing of
  the `pages` field on first citations of `@article` and `@review`
  entries (and their aliases) when the `postnote` is blank
* added support for the `\fullcite` and `\footfullcite` citation
  commands
* new citation commands: `idemcite`, `idemcites`, `footidemcite`,
  `footidemcites`
* added support for printing ISSNs with `issn` entry and bibliography
  options
* fixed `nameaddon` and `handle` fields printing in short citations

## 2020-09-29

* better punctuation handling in parenthetical citations, allowing
  examples in *CMOS* 15.24 and 15.30 (17th ed.)
* for `@reference` and `@inreference` entries, added support for
  printing the `organization` field in the author's position of short
  citations, fixing many of them (most of them? it was bad!)
* also for `@reference` and `@inreference` entries, allowed the
  `author` field to substitute for `organization` (not recommended but
  could prevent confusion in some cases)
* fixed `\cites` and `\parencites` for consecutive citations of the
  same author (most seriously affecting parenthetical citations but
  also standard and short citations in different ways)
* fixed parenthetical citations not printing volume numbers for
  certain collections

## 2020-09-07

* added support for revisers and expanded combinations of editor and
  translator types:

  - compiled by, comp., comps.
  - compiled and edited by, comp. and ed., comps. and eds.
  - compiled and revised by, comp. and rev., comps. and revs.
  - compiled and translated by, comp. and trans., comps. and trans.
  - edited by, ed., eds.
  - edited and compiled by, ed. and comp., eds. and comps.
  - edited and revised by, ed. and rev., eds. and revs.
  - edited and translated by, ed. and trans., eds. and trans.
  - revised by, rev., revs.
  - revised and compiled by, rev. and comp., revs. and comps.
  - revised and edited by, rev. and ed., revs. and eds.
  - revised and translated by, rev. and trans., revs. and trans.
  - translated by, trans.
  - translated and compiled by, trans. and comp., trans and comps.
  - translated and edited by, trans. and ed., trans. and eds.
  - translated and revised by, trans. and rev., trans. and revs.

* added support for citing prefaces (akin to citing afterwords,
  forewords, and introductions)
* fixed placement of `edition` relative to editors, translators, and
  such
* fixed short citations of `@review` entries failing to print a review's
  title
* fixed output of `@inreference` entries when they cross-reference a
  previously cited `@reference` entry
* fixed mismatch in output between `@article` and `@periodical` entry
  types
* fixed `\parencite` failing to print names in `afterwords`,
  `forewords`, and `introduction` fields

* fixed printing `transcomp` and `transed` bibliography strings when
  `transcomp+` and `transed+` were needed

## 2019-07-17

* fixed always printing the `date` field in an American format, rather
  than in formats set in localization files
* for documents not in English, check for `<language>-windycity.lbx`
  and, if available, use it instead of `american-windycity.lbx`
* defined `\textcite`, `\texcite*`, `\textcites` and `\textcites*`
  (useful for examples in *CMOS* 13.65)

## 2019-04-02

* fixed `\parencite` from printing a work's publication year twice
  under the preamble option `reflist`
* fixed the failure of the 3-em dash to print in bibliographies when
  compiling with different languages
* fixed `\autocite`; it should work for options `footnote`,
  `inline`, and `plain` and with all preamble options
* defined `\smartcite`, `\smartcite*`, `\smartcites`, and
  `\smartcites*`

## 2019-03-27

* fixed a bug that could prevent names in the `editora` field from
  printing in the author's position
* fixed typos that broke the `mathesis` entry type
* fixed `mathesis` and `phdthesis` entry types so that they don't need
  a `type` field to distinguish the MA from the PhD (only the `thesis`
  entry type needs it)
* improved support for newspapers and magazines with issue numbers
  (see updated documentation on how to implement it)
* added support for citing a newspaper's edition, such as 'Sunday Book
  Review'

## 2019-02-21

* fixed reviews with titles
* in reference lists, fixed `year` printing with `season` or `issue`
* much improved format of unsigned reviews in bibliographies and
  reference lists, in part restoring previous work set aside
* extended `swapvol` option to work with `letter`, `incollection`,
  `inbook`, and `bookinbook` entries that are cross-referenced to
  entries that work with `swapvol` (in effect, you can use `swapvol` not
  only with volumes in collections but with works in those volumes, such
  as chapters and articles)
* improved handling of editors and translators, including support for
  translators of a `maintitle`
* added `library` entry and preamble options to support the `library`
  field
* extended `swapauth` to work with `mvbook` and `mvcollection` entries
* added support for `\iffieldbibstring` in processing `edition` and
  `type` fields
* other bug fixes

## 2019-01-31

* added limited support for citing web pages and social media content
* added `listvols` entry option (see documentation)
* added `skipdate` entry option (see documentation)
* significant changes for tighter control of punctuation, among
  other things fixing the previous use of `postpunct`
* fixed printing of publication dates for some reports
* fixed `nameaddon` not printing after a 3-em dash in bibliographies
  (presumably, screen names should also print in this context; they do
  now)
* fixed a show-stopping bug in reference lists caused by the
  previous fix to `nameaddon`
* fixed reprints, cross-referencing in reference lists
* other bug fixes

## 2019-01-18

* reversed default for collections, printing information for volumes
  first; the option to reverse this is called `swapvol`
* changed option name `transfirst` to `swaptrans`
* fixed punctuation before `postnote` of articles and reviews (ugh!)
* changed processing of spacing and punctuation around `postnote` for
  all citations
* added support for swapping the place of an author with an editor or
  translator, as in *CMOS* 14.104
* extended the previous to cover a similar case in *CMOS* 14.122
* improved handling of name lists and cross-referencing
* removed no longer maintained citation commands
* other bug fixes and housekeeping

## 2019-01-07

* major additions and changes for processing collections
* fixed \parencite for unsigned articles
* fixed \parencite for cross-referencing
* fixed formatting of reviews
* added support for `autopunct` option and `postpunct` field for
  better handling of punctuation after citation commands (e.g.
  `\cite{something}` will end with a period, while `\cite{something};`
  will end with a semicolon)
* in light of the previous, changed \reprint command
* added support for `shortjournal` field for parenthetical citations
* simplified `parencite` and related macros
* improved handling of `year`, `endyear`, `bookyear`, and
  `endbookyear` fields, ensuring that the publication date of the last
  mentioned work gets printed in bibliographies and reference lists
* many bug fixes

## 2018-12-09

* simpler processing of author's position
* added support for common reference works, such as dictionaries and
  encyclopedias
* fixed `\defbibcheck` for reference works
* fixed short option printing urls and related data on first citations
* some fixes, though incomplete, for reviews
* other fixes for spacing and punctuation

## 2018-12-05

* added much better support for cross-referencing collections in notes
  and bibliographies, including enhanced support for treating multivolume
  collections as a single work
* support for short format of citations, with `short` and `ibid`
  preamble options
* added support for self-published books
* added support for electronic article IDs
* added support for `shortauthor` namelist
* better processing of reviews, though still limited
* fixed and improved multicite output
* undid change to `noauth` entry option (it was right the first time!)
* many bug fixes (mainly spacing, punctuation, and toggles)
* new documentation

## 2018-11-26

* fixed `noauth` entry option (it should only affect notes)
* fixed `inst+loc+date`
* following *CMOS*, made `cite:short` print just a work's title
  without the name of the collection
* fixed name formatting for affixes like 'Jr.' in notes (no comma
  before them, unlike in bibliographies, where names are inverted)
* limited support for copublication
* limited support for publication times
* added `\footcite*` command and updated documentation

## 2018-11-23

* improved and in some cases fixed processing of numbers,
  dates, and issues of periodicals
* much better support for unsigned articles
* fixed `type` field format
* fixed double printing of year for theses and dissertations in
  the author-date system
* fixed punctuation after 'Special issue' in bibliographies
* fixed obscure punctuation issue with *notewrapper commands
* added support for shorthandintro and improved handling of shorthands
* updated field format for DOIs
* update name formatting for affixes like 'Jr.'

## 2018-11-17

* replaced `\ifthenelse` with commands from etoolbox
* better handling of editors for a series, maintitle, or issuetitle
* limited support for `endmonth` field for periodicals
* fixed extra space from `multicitedelim`

## 2018-11-14

* finally got a handle on the author-date format for periodicals,
  rolling back some recent changes (ugh!)
* put back preamble options `useeditor` and `usetranslator`, which
  are necessary after all (double ugh!)
* more readable and arguably simpler date processing for periodicals
* added preamble option `ibid` to prepare for the 17th edition of
  *CMOS*
* updated `windycity.tex` to reflect the last point, also to make use
  of `optionlist`
* remove unused entries from `windycity.bib` for the 15th edition of
  *CMOS*

## 2018-11-13

* fixed spacing of date for periodicals (resulting from recent support
  for `endday` field)
* fixed spacing between volumes and pages in author-date system for
  periodicals
* support names of anonymous authors as in *CMOS* 14.80 (16th edition)
  and *CMOS* 14.79 (17th edition)

## 2018-11-09

* for articles etc., limited support for `season` field
* limited support for `endyear` and `endorigyear` fields
* removed unused preamble options and commented code
* fix `inreference` bibliography alias

## 2018-11-02

* fixed author-date system printing the year of many articles twice
* fixed author-date system printing the year between an author's name
  and the field `nameaddon`
* fixed bibliography driver for shorthands that caused it to print
  just titles, rather than full entries
* added support for `endday` field
* `addendum` field prints only in bibliographies and reference
  lists, not in notes
* set `parentracker` preamble option
* set `minxrefs` preamble option
* `collsonly` preamble option sets `minxrefs=1`
* changed `pagetracker` preamble option from `true` to `page`
* edits and fixes to `windycity.sty` and `windycity.tex`

## 2018-10-20

* fixed broken date formatting in author-date citations
* changed `\DeclareSortingScheme` to `\DeclareSortingTemplate`
* changed preamble option `labeldate` to `labeldateparts`
* changed special field `extrayear` to `extradate`
* bumped minimum compatible release to biblatex 3.8
* other minor changes for the version bump

## 2015-12-28

* added missing `\setunit` for when `bybookauthor` prints an author's
  name and the collection has an editor, translator, or compiler

## 2015-07-08

* removed an unused bibmacro
* minor edits and fixes to `windycity.sty` and `windycity.tex`
* minor edits to readme
* removed an empty line from `windycity.bib`
* changed the version number format to match the release date

## 2014-03-21

* improved and fixed cross-referencing of collections to other collections
* fixed missing publication year in notes under option `reflist`
* fixed incorrect printing of `volumes` under option `reflist`
* minor fixes
* updated documentation

## 2014-03-02

* greatly simplified the handling of editors and translators
* changes and fixes to `incollections`, `ed+vol+part+etc`, and
  associated macros, especially affecting the placement of a book's
  series in relation to other elements
* added and changed placement of `note` for some entry types
* added support for abstracts (via `note` for `@article`)
* simplified `reviews`
* made `@unpublished` an alias of `@thesis`
* other minor changes and fixes
* updated `windycity.tex` and `windycity.bib`

## 2014-02-26

* initial release

