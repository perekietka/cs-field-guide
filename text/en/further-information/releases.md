# Releases

This page lists updates to the Computer Science Field Guide. All notable changes to this project will be documented in this file.

{panel type="What numbering system do we use?"}

We base our numbering system from the guidelines at [Semantic Versioning 2.0.0](http://semver.org/spec/v2.0.0.html), however since our project started before it was migrated to GitHub, the first open source release is being labeled as `v2.0`.

Given a version number MAJOR.MINOR.HOTFIX:

- MAJOR version change when major text modifications are made (for example: new chapter, changing how a curriculum guide teaches a subject).
- MINOR version change when content or functionality is added or updated (for example: new videos, new activities, large number of text (typo/grammar) fixes).
- HOTFIX version change when bug hotfixes are made (for example: fixing a typo, fixing a bug in an interactive).
- A pre-release version is denoted by appending a hyphen and the alpha label followed by the pre-release version.

{panel end}

We have listed major changes for each release below.

## Current Release

### v2.6.0

**Release date:** 16th June 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.6.0)

**Notable changes:**
- **New feature:** PDF output - A downloadable PDF of both student and teacher versions is now available from the homepage. The PDF also functions well as an ebook, with functional links to headings, glossary entries, interactives, and online resources.
- **New feature:** Printer friendly webpages - When printing a page of the CSFG through a browser, the page displays in a printer friendly manner by hiding navigational panels, opening all panels, and providing extra links to online resources.
- **New interactive:** The [binary cards interactive](interactives/binary-cards/index.html) emulates the Binary Cards CS Unplugged activity, used to teach binary numbers.
- **New interactive:** The [high score boxes interactive](interactives/high-score-boxes/index.html) was developed to give an example of searching boxes to find a maximum value to the student.
- **New interactive:** The [action menu interactive](interactives/action-menu/index.html) is a small dropdown menu with one option that has severe consequences, but no confirmation screen if user selects that option (used to demonstrate a key HCI concept).
- **Updated interactive:** The [trainsylvania interactive](interactives/trainsylvania/index.html) (and supporting images/files) have been given a fresh coat of colour and a new station name.
- **Updated interactive:** The [trainsylvania planner interactive](interactives/trainsylvania-planner/index.html) is used alongside the trainsylvania interactive, and allows the user to input a path of train trips to see the resulting destination.
- **Updated interactive:** The [base calculator](interactives/base-calculator/index.html) allows a student to calculate a number, using a specific number base (binary, hexadecimal, etc).
- **Updated interactive:** The [big number calculator](interactives/big-number-calculator/index.html) allows a student to perform calculations with very large numbers/results.
- **Website improvements:** Redesigned homepage and footer with useful links and a splash of colour. Math equations are now line wrapped, and MathJax is loaded from a CDN. Images can now have text wrapped around them on a page.
- **Generation improvements:** Improvements to internal link creation (glossary links in particular). Separated dependency installation from generation script (see documentation for how to install and run generation script).
- **Project improvements:** Added documentation for contributing to and developing this project, including a code of conduct.

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.5.0...v2.6.0).

## Older Releases

### v2.5.0

**Release date:** 13th May 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.5.0)

**Notable changes:**
- The Data Representation chapter has been rewritten and reorganised to be easier to follow, and three NCEA assessment guides have been written for students aiming for merit/excellence:
  - [Numbers (Two's Complement)](curriculum-guides/ncea/assessment-guide-level-2-excellence-data-representation-numbers.html)
  - [Text (Unicode)](curriculum-guides/ncea/assessment-guide-level-2-excellence-data-representation-text.html)
  - [Colours (Various bit depths)](curriculum-guides/ncea/assessment-guide-level-2-excellence-data-representation-colour.html)

  The chapter and assessment guides have been rewritten to take account of new feedback from the marking process and our own observations of student work.

  As part of the rewrite of the Data Representation chapter, the following interactives were developed:
  - New interactive: The [unicode binary interactive](interactives/unicode-binary/index.html) displays the binary for a given character (or character by decimal number) dynamically with different encodings.
  - New interactive: The [unicode character interactive](interactives/unicode-chars/index.html) displays the character for a given decimal value.
  - New interactive: The [unicode length interactive](interactives/unicode-length/index.html) displays the length (in bits) of text encoded using different encodings.
  - Updated interactive: The [colour matcher interactive](interactives/colour-matcher/index.html) has been redesigned to display values in binary, plus allow students to see and edit the bit values. The interface has also been restructured for readability and ease of use.

  The old version of the Data Representation chapter can be [found here](http://csfieldguide.org.nz/releases/2.4.1/en/chapters/data-representation.html).
- Website improvements: A new image previewer was implemented, along with bugfixes to iFrame and panel rendering.
- Generation improvements: The Markdown parser has been replaced due to existing parsing issues. The new parser also gives us a large performance boost. A text box tag has also been added to highlight important text.

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.4.1...v2.5.0).

### v2.4.1

**Release date:** 29th April 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.4.1)

**Notable changes:**
- Fixed version numbering system to allow hotfix changes

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.4...v2.4.1).

### v2.4

**Release date:** 29th April 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.4)

**Notable changes:**
- Large number of typo, grammar, link, and math syntax fixes and also content corrections by contributors.
- New interactive: Added [GTIN-13 checksum calculator interactive](interactives/checksum-calculator-gtin-13/index.html) for calculating the last digit for a GTIN-13 barcode.
- Updated interactive: The [regular expression search interactive](interactives/regular-expression-search/index.html) has been updated and added to the repository.
- Updated interactive: The [image bit comparer interactive](interactives/image-bit-comparer/index.html) has been updated and added to the repository. It also has a [changing bits mode](interactives/image-bit-comparer/index.html?change-bits=true) which allows the user to modify the number of bits for storing each colour.
- Added XKCD mouseover text (similar behaviour to website).
- Added feedback modal to allow developers to directly post issues to GitHub.
- Added encoding for HTML entities to stop certain characters not appearing correctly in browsers.
- Added summary of output at end of generation script.
- Added message for developers to contribute in the web console.

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.3...v2.4).

### v2.3

**Release date:** 10th March 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.3)

**Notable changes:**
- Readability improvements to text within many chapters (grammer issues/typos) and to the Python scripts within the Algorithms chapter.
- Updated interactive: The RSA [encryption](interactives/rsa-no-padding/index.html) and [decryption](interactives/rsa-no-padding/index.html?mode=decrypt) interactives within Encryption have been updated and added to the repository.
- Updated interactive: The [searching algorithms interactive](interactives/searching-algorithms/index.html) within Algorithms have been updated and added to the repository.
- Updated interactive: The [word filter interactive](interactives/regular-expression-filter/index.html) within Formal Languages have been updated and added to the repository.
- Updated interactives: Both the [MIPS assembler](interactives/mips-assembler/index.php) and [MIPS simulator](interactives/mips-simulator/index.php) were made open source by the original author, and we were given permission to incorporate our repository, and have been added to Programming Languages.
- A list of all interactives are now available on the [interactives page](further-information/interactives.html).

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.2...v2.3).

### v2.2

**Release date:** 19th February 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.2)

**Notable changes:**
- New interactive: Parity trick with separate modes for [practicing setting parity](interactives/parity/index.html?mode=set), [practicing detecting parity](interactives/parity/index.html?mode=detect), and [the whole trick](interactives/parity/index.html). Also has a [sandbox mode](interactives/parity/index.html?mode=sandbox).
- Updated interactives: Two colour mixers, one for [RGB](interactives/rgb-mixer/index.html) and one for [CMY](interactives/cmy-mixer/index.html) have been added.
- Updated interactive: A [colour matcher interactive](interactives/colour-matcher/index.html) has been added for matching a colour in both 24 bit and 8 bit.
- Updated interactive: A [python interpreter interactive](interactives/python-interpreter/index.html) has been added for the programming languages chapter.
- Website improvements: Code blocks now have syntax highlighting when a language is specified, dropdown arrows are fixed in Mozilla Firefox browsers, and whole page interactives now have nicer link buttons.

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.1...v2.2).

### v2.1

**Release date:** 12th February 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.1)

**Notable changes:**
- Fixed many broken links and typos from 2.0.0
- Added calculator interactives to Introduction
- Added RSA key generator to Encryption
- Rewritten Braille Section in Data Representation

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.0...v2.1).

### v2.0

**Release date:** 5th February 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/releases/tag/v2.0)

**Notable changes:**
- First open source release
- Produces both student and teacher versions
- Produces landing page for selecting language
- Added new NCEA curriculum guides on Encryption and Human Computer Interaction

A full list of changes in this version is [available on GitHub](https://github.com/uccser/cs-field-guide/compare/v2.0-alpha.3...v2.0).

**Comments:**
The first major step in releasing a open source version of the Computer Science Field Guide.
While some content (most notably interactives) have yet to be added to the new system, we are releasing this update for New Zealand teachers to use at the beginning of their academic year.
For any interactives that are missing, links are in place to the older interactives.

### v2.0-alpha.3

**Release date:** 29th January 2016

**Downloads:** [Source available on GitHub](https://github.com/uccser/cs-field-guide/compare/d8a69d50575cac8c4e2686ee4d9af7c22b7131a7...v2.0-alpha.3)

### v2.0-alpha.2

**Release date:** 25th January 2016

### v2.0-alpha.1

**Release date:** 2nd December 2015

**Comments:**
Released at CS4HS 2015.

### 1.?.?

**Release date:** 3rd February 2015

**Comments:**
The last version of the CSFG before the open source version was adopted.

[This release is archived for viewing here](http://www.csfieldguide.org.nz/releases/1.9.9/).

{version-specific-content version="teacher"}
[The teacher version is archived for viewing here](http://www.csfieldguide.org.nz/releases/1.9.9/teacher/).
{version-specific-content end}
