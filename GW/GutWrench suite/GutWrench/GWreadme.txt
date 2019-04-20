This is the ReadMe file for GutWrench v. 1.3, a Windows-based tool to aid in post-processing of e-book texts at Distributed Proofreaders.

The latest version of GutWrench is always available at:
http://www.pgdp.net/tools/GW.zip


NEW IN THIS VERSION (1.3)

--Mapping of Illustrations has been made a separate option.
--Mapping of Footnotes.

NEW IN VERSION (1.2)

--In checking the text, flagging long lines is now optional.
--The feature for joining short lines (a crude re-wrap) has been deleted. (A similar feature is now included in GutSweeper.)

NEW IN VERSION 1.1

--Added a menu preference for in-line or out-of-line footnotes; footnotes of the wrong type are flagged.

NEW IN VERSION 1.0

--Language menu allows selection of multiple lists of stealth scannos.

NEW IN VERSION 0.9

--Concordance Map makes a list of all words used in the text, their frequencies, and line number in which they are first used. (This may take several minutes to run.)
--Scannos are searched for differently: short scannos (< 5 letters) must appear in the text as complete words (surrounded space or punctuation) in order to be flagged; long scannos may be parts of longer words. The accompanying GWscanno.txt plug-in file has been modified accordingly.
--Record Mode causes maps and error messages to be saved in external text files. (This was always the case previously; writing thses files can now be turned off.)

NEW IN VERSION 0.8

--Added a capability to open files in other folders (Open command under the File menu)

NEW IN VERSION 0.7

--Maps of Hyphenated Words and Words having Accented and Other Special Characters
--The Hyphen/Dash check no longer flags all isolated hyphens (since the above works so well!)

NEW IN VERSION 0.6

--Expert Mode: few and briefer messages; non-interactive joining of short lines and removal of Page Separators.
--Silent Mode: fewer beeps.
--Page Map tabulates also "thought breaks" (e.g., "2TB" means the page has two thought breaks)
--Rewrap Text function removed, incorporated into a new sister code, GutHammer (included with this download package).

NEW IN VERSION 0.5

--Rewrap Text function (subsequently removed in Version 0.6; see above)
--Hyphen/dash check now also flags all isolated hyphens (e.g., within hyphenated words)

NEW IN VERSION 0.4

--"Page" map function summarizes special markups on each page.
--Hyphen/dash check ignores page separators.


INSTRUCTIONS FOR USE

The e-book file must reside in the same Windows directory (folder) as the GutWrench.exe file and sub-directory GWplugins, which contains the 3 GutWrench auxiliary files: GWimposs.txt, GWimprob.txt, and GWscanno.txt. The e-book file must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left. Then select which operations you would like to perform from among the check-box choices.


MAP TEXT

There are six "Map Text" functions: 

"Character" records the number of occurrences of each character in the entire text, and displays a table showing in each row the numeric value of each character, the character itself, and the number of occurrences. This is useful in finding the presence of illegal characters and in detecting whether there are the same numbers of opening and closing parentheses and brackets. Characters that are illegal the Latin-1 set (ISO-8859-1) are highlighted as "non-Latin-1." 

"Page" makes a one-line-per-page summary of the text. You must keep the page separators in the text file for this to work properly! Each line lists, for each page:
1) number of blanks lines ("paragraphs")
2) number of hyphens (as individual characters; i.e., a two-hyphen dash counts as two hyphens)
3) number of asterisks
4) number of sets of <i>italic</i>, <b>bold</b>, and <sc>small caps</sc> markups; a warning is noted if they do not match on each page, so this is always a good check to run
5) number of "low line" characters ("_"); a warning is noted if the number is odd
6) list of unusual and accented characters
7) number of (properly formatted) "thought breaks".
If a page is empty (no lines), it is so flagged; likewise if a page contains only blanks. If a page contains only a single line of text, it is merely printed as the summary!
When printed out, this summary may be quickly compared with the scan images to verify that all these items have been caught by the proofers. (I find it especially useful for identifying missing "thought breaks" and italic markups.)

An example line of a Page Map:

  124:4¶7|6-|12*|<i>3</i>|<b>4</b>|5_|ëæ|()[][]{}|2TB

means:
124 = page number 124
4¶7 = 4 blank lines at the top of the page (this page must start a new chapter) and 7 other blank lines
6- = 6 hyphen characters (could be parts of "dashes")
12* = 12 asterisks (including the 2 thought breaks)
<i>3</i> = 3 sets of matching italics mark-ups
<b>4</b> = 3 sets of matching bold mark-ups
5_ = 5 low-line characters "_"
ëæ = list of special and accented characters that appear on this page (in order)
()[][]{} = list of parentheses, square brackets, and braces that appear on this page (in order)
2TB = 2 (properly formatted) "thought breaks" (5 *'s separated by 7 spaces each); these are counted among the 12 asterisks.

"Hyphenations" and "Accents" work similarly. "Hyphenations" searches for all hyphenated words and tabulates them. Then it flags occurrences of the same words with the hyphens removed. For example, if it finds occurrences of "to-day" and "to-morrow", then it flags all occurrences of "today" and "tomorrow". This function also helps you find other hyphenation errors (hyphen does not belong, or hyphen in place of a dash). 

"Accents" performs a similar function for words containing accents (also the ae ligature). For example, if it finds occurrences of "élite" and "cæsar", it tabulates them and flags occurrences of "elite" and "caesar".

"Concordance" makes a concordance of the text: a list of all the words used, their frequencies, and the line number in which they are first used. This may take several minutes to run, with the time increasing hyperbolically with the length of the text.

"Illustrations" lists all lines of text containing "[Illustration".

"Footnotes" lists all lines of text containing "[Footnote". This is useful in checking that Footnotes have been number consecutively.

The maps are also saved in a text file named "GWmaps.txt" (unless Record Mode is turned off).


CHECK TEXT

The "Check Text" functions display messages in the field at the right of the GutWrench window; these are also recorded in an output text file, named GWerrors.txt (unless Record Mode is turned off).

The "Hyphens/Dashes" check flags:
1) hyphens and dashes next to other punctuation
2) series of five or more hyphens
3) hyphens and dashes at the beginning or end of a line of text
(Page separators are ignored.)
Expert Mode (under the Modes menu) is recommended for checking Hyphens and Dashes.

The "Italics/Bold" check flags:
1) spaces and punctuation immediately after <i>, <b>, or <sc>, or before </i>, </b>, or </sc> (not all of these are errors)
2) <i>, <b>, or <sc> at the end of a line, and </i>, </b>, or </sc> at the beginning

The "Other Errors" check flags:
1) Unmatched poetry /*..*/, block quote /#..#/, and sic /$..$/ markup
2) Double spaces (except within poetry/block-quote/sic)
3) Long lines (more than 75 characters)
4) "Impossible" character sequences, as listed in the file GWimposs.txt. Most of these are punctuation errors, but some are scanno-type errors (e.g., "l", not "1", next to another number).

The "Check Text" functions "Other errors" and "Warnings" search for sequences of characters in the files GWimposs.txt and GWimprob.txt, which must be contained in the sub-directory "GWplugins". For example, "Other errors" searches the e-book file for occurrences of each line of the file GWimposs.txt, which contains sequences of characters (mostly punctuation) that are practically impossible to encounter; these are flagged as Errors (**). These files are simple text files that may be edited using any text editor (Windows Notepad or any word-processing application); be very careful about any blank spaces, which will be interpreted as part of the string of characters to be flagged; comment lines may be included in these files by beginning the line with a backslash "\".

The "Scannos" function searches for possible stealth scannos. These are read into GutWrench from several files: GWscanoE.txt (which contains possible English scannos), GWscanoOE.txt (which contains possible "ftealth fcannof", which are English words that are confused when the OCR interprets an old-time "long S" character as a modern "f"), GWscanoF.txt (French stealth scannos), and GWscanoO.txt (stealth scannos in other languages). These files must also reside in the GWplugins sub-directory. The choice of which of these files are to be searched is made under the Languages menu; note that these selections are not mutually exclusive--it is possible to search through multiple files at once.

Short words (4 or fewer letters) listed in these files are searched for as actual words; this means that if, say, "be" is listed in GWscanoE.txt, then the word "be" standing by itself (surrounded by spaces or punctuation) in the text will be flagged, but not its presence within, say, the words "abet" or "best". Longer words (5 or more letters) are searched for as character strings; this means that if "board" is listed in GWscanoE.txt, then also "boards", "boarded", "boarding", and "aboard" will all be flagged. This list contains stealth scannos in a very broad sense, including words that sometimes appear with or without hyphens (such as "to-day/today") and with or without accents (such as "coupé/coupe"). Editing of this file to suit the user's particular level of paranoia or to better suit a particular book is encouraged. 


MODIFY TEXT

The "Modify Text" functions produce an output text file with the selected changes. Any or all functions may be selected by checking their associated boxes. The "Remove poetry markup lines" also warns when there are other characters after the /* or */ markup; if so, it asks the user whether the line should be removed anyway.

If Expert Mode is not selected, the "Remove Page Separators" function works interactively; the suspected Page Separator is displayed in the field at the right, and the user is asked whether it should be removed. If Expert Mode is selected, all the Page Separators will be removed without any prompting of the user. 

In interactive mode (Expert Mode = Off), this process can be cancelled (aborted) by the user; the output file will be complete but only the part worked on up to that point will be modified.

The output file containing the modified text is named GWout.txt. The original file is never changed.


MODES MENU

--Expert Mode requests fewer and briefer messages; also, "Remove Page Separators" and "Join Short Lines" (see MODIFY TEXT above) operate non-interactively, but run to completion without prompting the user.
--Silent Mode requests fewer warning beeps.
--Record Mode causes maps and error messages to be saved in external text files. The default is Record Mode = On; turning it Off prevents these files from being created or written over. 


HOW I USE IT

How I use GutWrench in the overall process of post-processing (this applies to an easy text, with in-line footnotes; see the PP FAQ for more things to search for):

1. First use an editor (Notepad is fine) to run thru the entire file, in order to:
    --check and clean up /*...*/ and similar markup.
        ==delete */* in the middle of poetry.
        ==change /*...*/ to /#...#/ around blocks quotes
        ==change /*...*/ to /$...$/ around tables (so they will not be indented)
        ==change /*...*/ to /$...$/ around poetry with variable indents (set these indents by hand)
    --check and correct glaring proofer's errors and "questioning" asterisks.
    --format the first pages and the chapter headings, making sure they're all there and in order.
    --clean up around page separators:
        ==delete extra blank lines.
        ==leave one blank line _after_ (so you know _you_ put it there) the separator if the page break coincides with a new paragraph.
        ==add other blank lines as needed after the separator, such as to indicate a new chapter.

2. Run Gutcheck (with no options selected) and GutWrench to map the text and check for errors (at this point, I select only "Other Errors"). I compare the GutWrench Page Map (I print this in two columns) with the scanned images (I use IrfanView's Slide Show feature) to make sure that all italic markups, thought-breaks, accented and other special characters, and, if I feel really picky, hyphens/dashes and asterisks, have been picked up by the proofers (at least check italics and thought-breaks). I keep a copy of this corrected text file (with the page separators intact) for when I later need to refer to the scan images.

3. Run GutWrench to modify the file:
    --Delete trailing blanks.
    --Delete page separators (don't do this if you want to number the pages, such as in the HTML).
These can all be done in a single run of GutWrench. Note that GutWrench does not modify the input file, but creates a new file GWout.txt that contains all these changes. Careful! if you keep running it using the same input file, it will just keep over-writing the GWout.txt file.

4. In an editor, rejoin hyphenated words that crossed between pages.

5. Now thoroughly check for errors with:
    --GutWrench (turn on all the Check File options; I prefer to go through them one-by-one)
    --Gutcheck (with the -v option for "verbose")
    --a spell-checker (I use MSWord)
Both GutWrench and Gutcheck run very quickly, so I usually keep repeating these, performing corrections in between, until I've eliminated all the real errors (both give some "false-positive" warnings, especially GutWrench's Warnings and Scanno checks). But to avoid duplication of effort, I try to run the spell-checker through the entire file in a single sitting.

6. Rewrap text. For books with simple formatting (poetry, tables, block quotes, etc., but not embedded poetry inside block quotes, etc.), GutHammer is sufficient; you will then have to set up the indentation for the specially formatted sections by hand (either before or after rewrapping). For more complicated books, I recommend Big_Bill's tool, RewrapIndent. Both of these tools also delete trailing blanks and poetry and other markups. (DO NOT use PRTK's Rewrap Text function! It will introduce errors into your text.) After using either one, I quite fussily follow with some manual smoothing of the right margin, also visually checking that abbreviations and such are not split across lines.

7. If you are uploading directly to Project Gutenburg, edit the text to change the <i>italic markups</i> to _underlines_. This can also be done with GutHammer.

8. Perform final checks with Gutcheck and GutWrench, and make final inspection with a text editor.


Address all comments to BillFlis through the Distributed Proofreaders Forum or via email at flis@detk.com.