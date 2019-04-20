This is the ReadMe file for GutCutter v. 0.3.12, a Windows-based tool to aid in preparing HTML versions of e-book texts at Distributed Proofreaders. Its purpose is to add most of the markups needed to make an HTML version.

The latest version of GutCutter is always available in the GutWrench download package at:
http://www.pgdp.net/tools/GW.zip

NEW IN THIS VERSION (0.3.12)

--Allows special styles that produce only plain-text or HTML output.
--A special "Show Errors" style has been added.

NEW IN VERSION 0.3.11

--Does not add <p>...</p> tags around a line that ends with </hx> tag. 
--Handles /p...p/ markup around poetry.

NEW IN VERSION 0.3.6

--Handles pages numbered with Roman numerals (i.e., "xiv.png" on the Page Separator).

NEW IN VERSION 0.3.5

--Includes help for constructing Tables of Contents and lists of illustrations.

NEW IN VERSION 0.3.4

--Does not put <p>...</p> tags around centered text having <center>...</center> tags.

NEW IN VERSION (0.3.2)

--Does not remove Page Separators from plain-text version.
(These may be replaced by, say, page numbers or may be removed by GutHammer or other program.)

NEW IN VERSION 0.3

--More flexible definition of styles.
--Style Menu replaced by combo box.

NEW IN VERSION 0.2

--Style definitions may make use of Regular Expressions.
--Addition of Header or Trailer files can be optionally turned off.


INSTRUCTIONS FOR USE

GutCutter takes as input a "well-marked-up version" of an e-book. A "well-marked-up version" is a text that has been readied for PPing at DP, with the addition of a few additional markups (mostly HTML). These extra markups include:
--/#...#/ about block quotes
--/*...*/ about poetry
--/$...$/ about tables and other text that should not be rewrapped
--HTML Header tags: <h1>...</h1>, etc.
The file must reside in the same Windows directory (folder) as the GutCutter.exe file and sub-directory GCstyles, which contains several auxiliary files. The e-book file must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left.


TO DISPLAY ERRORS

Run as above, but select the style named "Show Errors (HTML only)". Suspected errors will appear highlighted when the HTML output file GCout.htm is opened in a browser. Hovering the mouse over the highlighted text will (usually) indicate why it is suspicious.


OUTPUT AS ...

Select "Plain Text" to convert a well-marked-up version into a plain-text version.

Select "HTML" to convert a well-marked-up version to an HTML version in a style selected under the Style Menu.

Some special styles allow only one type of output. If this is the case, the appropriate output type will be automatically selected, and the button corresponding to the other type will be disabled.


MODIFY TEXT

The "Modify Text" function makes numerous changes to the text to bring it very close to the final plain-text or HTML version. This program is intended to do 90% of the work for you. The result is always output as GCout.txt for plain text and GCout.htm for HTML. If the Style has been set up to do so, data for the Table of Contents and list of illustrations will be output to the text file named GCtoc.txt (the form of this file will be different according to whether a plain-text or HTML version has been generated). 


MODES MENU

--Interactive Mode asks the user for confirmation before making the style changes to the text. (However, <p>...</p> markups are still automatically added if HTML Output is selected.)
--Silent Mode requests fewer warning beeps.


HOW IT WORKS (mainly for geeks!)

To generate HTML, GutCutter works internally in three stages. In the first stage, it adds <p>...</p> about each paragraph and about each line of poetry (within /*...*/ markups). It identifies the beginning of a paragraph as a line of text that is preceded by a blank line. Similarly, the end of a paragraph is identified as being followed by a blank line (or by a Page Separator followed by a blank line). Exceptions (which don't get <p> or </p>):
--Blank lines
--Lines starting with "[Illustr", "[Footnot", or "       *" (Thought Breaks or "Small" Breaks)
--Markup lines: /*, */*, */, /#, #/, /$, $/
--Header lines, beginning with "<h" or ending with "</hX>" (where X is a digit)

Also, blank lines in poetry (which separate stanzas) are (temporarily) replaced by */* (this allows them to be identified and operated on in stage two). In generating plain text, this first stage is skipped.

In stage two, certain strings are replaced according to "rules" contained in the selected Style plug-in file (GCstyle0.txt, etc.). Rules are defined in two ways: as String substitutions and as Regular Expressions. A typical rule might read:

s\/*\<pre>\Poem begins

which is divided into four parts by the backslashes (\). The first part, here "s", identifies this as a String substitution. This rule means that every occurrence of the string "/*" is to be replaced by the string "<pre>"; the last part, "Poem begins", is a comment.

Rules defined by Regular Expressions are identified by "r" or "R" as the first character. Since backslashes occur frequently in Regular Expressions, GutAxe takes the second character of the rule as the delimiter; the low-line character "_" or tilde "~" are convenient choices. Thus, the rule: "r_/\*_<pre>_Poem begins" performs the same string substitution as the above example. The advantage of Regular Expressions is their power and flexibility in defining complex text manipulations in compact rules.

Rules starting with "o" or "O" request output to the file GCtoc.txt. Generally, this is used to collect data to be used in an added Table of Contents and/or list of illustrations. The contents of this file may be copied into the appropriate place in the main file and edited into final shape. This saves having to collect all this information by hand. These output rules are always defined in terms of Regular Expressions. For example, the rule:

o_<h2>([^<]+)<\/h2>_$1_Save heading.

will write the text between <h2>...</h2> markup to the file GCtoc.txt.

The order of operations on the text is dictated by the order of the lines in the Style plug-in. Therefore, if "*/*" is to be changed back into a blank line, the line

s\*/*\\Blank line in poetry

must appear before the above example lines, otherwise "*/*" will be changed to "*<pre>". Likewise, DP Page Separators (which contain long series of hyphens) must be treated before converting double-hyphens to HTML dash symbols.

In the third stage, the final output file is created from the Header plug-in associated with the selected Style, the modified text, followed by the selected Trailer plug-in. Note that a Header and Trailer are added even to plain-text output files; this can be useful when working on a series of similar publications, such as periodicals, that all share similar beginning and/or ending material.


THE PLUG-IN FILES

GutCutter is accompanied by several auxiliary text files. All of these may be edited by the user. These must be contained in a folder named GCstyles, which must be in the same folder as the GutCutter application.

The master plug-in, named GCdefine.txt, tells GutCutter which files should be used with each style. A style may be considered a complete set of guidelines for preparing both the plain-text and HTML versions of a text.

For each style, six files must be defined:
1. Plain-text style-changes file.
2. Plain-text header file.
3. Plain-text trailer file.
4. HTML style-changes file.
5. HTML header file.
6. HTML trailer file.

The style-changes files contain rules for converting markups to the appropriate format. For example, in preparing an HTML version, /#...#/ is converted to <blockquote>...</blockquote>. Depending on the style, the five-* Thought Break will be converted to <hr> or <hr />. And so on. In preparing the plain text, HTML Header markups <h2>...</h2> et al. may be converted to HTML Bold markups <b>...</b>, which are understood by most of the DP Post-Proofing tools (all of the GutWrench suite).

The header and trailer files are appended to GutCutter's output files.

Currently available styles include:

1. "Vanilla" HTML is intended to be similar to what is output by Donovan's pg2html program. The associated Header and Trailer files are taken from pg2html output. This style has not yet been tested.

2. Jon Ingram's style for "Punch" magazine. This uses XHTML 1.0. It has been thoroughly tested.

3. Jon Ingram's style for "The Mirror". This also uses XHTML 1.0. It has been tested somewhat.

4. Sci.Am., for the Scientific American uberproject. This uses standard HTML. It has not been tested.

5. Jon Ingram's style for the "Notes & Queries" periodical. This also uses XHTML 1.0. It has been tested somewhat.

6. "The Full Monty". This style incorporates as many special elements as possible, along the lines of styles #2 and #3; also uses XHTML 1.0. This is intended as a demonstration of the power of GutCutter.

New styles may easily be added by editing the GCdefine.txt file and preparing the associated style-changes, header, and trailer files.


HOW I USE IT

See the accompanying files "How to do Punch.txt", "How to do Mirror.txt", "How to do Notes & Queries.txt", and "How to do The Full Monty.txt".


WHAT IT CANNOT DO

Unlike pg2html, GC is not intended to automatically handle purely plain-text files; mark-ups are expected!


Address all comments to BillFlis through the Distributed Proofreaders Forum or via email to flis@detk.com.