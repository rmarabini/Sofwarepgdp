This is the ReadMe file for GutSweeper v. 0.7, a Windows-based tool to aid in post-processing of e-book texts at Distributed Proofreaders. The main function of GutSweeper is to clean up obvious errors in an e-text to prepare it for post-processing. First, it divides long lines of text to conform to a maximum desired column width. It also does some general cleaning up: removes trailing and double blanks, and deletes blank lines at the bottoms of pages (before the Page Separators). A text-checking feature insures that it will not be confused by erroneous poetry and other mark-ups (be sure to run this first!). GutSweeper is intended to be the very first tool used on an e-book for post-processing. It serves to save some manual labor as well as to reduce the number of error messages generated in subsequent runs of Gutcheck and GutWrench.

The latest version of GutSweeper is always available at:
http://www.pgdp.net/tools/GW.zip

NEW IN THIS VERSION (0.7)

--OE and oe ligature characters may be replaced with [OE] and [oe]; this is the default setting.

NEW IN VERSION 0.6

--Lines shorter than a specified length may be joined to previous lines.

NEW IN VERSION 0.5

--"AE" and "ae" ligatures may be split.
--Spaces within abbreviations may be closed up.
--The default setting on "naked" hyphens and dashes is to merely flag them.

NEW IN VERSION 0.4

--"OE" and "oe" ligatures may be split.

NEW IN VERSION 0.3

--"Naked" hyphens and dashes at the beginnings and ends of lines may be "dressed" or flagged.
--A little foolproofing: You must now first Check the text before you can Modify it.
--Some changes made to the text by the Modify-Text function are logged in a file.
--"Warnings" (which are for information only) are now called "Alerts".

NEW IN VERSION 0.2

--Interior poetry mark-up "*/*" is detected during Modify Text, and the user is offered the option of deleting the line.
--Poetry and other mark-ups with extra characters are detected during Modify Text and the user is offered the option of cleaning up the line by deleting the extra characters.
--Double (and multiple) blanks are now flagged in the Check-Text function as merely alerts, not errors, since these can be corrected (merged) by the Modify-Text function.

The latest version of GutSweeper is always available as part of the zipped GutWrench download file at:
http://frankfordinstitute.bravepages.com/GutWrench.htm

INSTRUCTIONS FOR USE

The e-book file must reside in the same Windows directory (folder) as the GutSweeper.exe file. The e-book file must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left. Then click "Check Text". Finally, select the "Modify Text" functions you would like to perform, and click "Modify Text". It is recommended that all Modify Text functions be selected.

CHECK TEXT

The "Check Text" function displays messages in the field at the right of the GutSweeper window; these are also recorded in an output text file, named GSerrors.txt. Its main purpose is to check for unmatched and nested poetry /*..*/, block-quote /#..#/, and stet/sic /$..$/ mark-ups. It is necessary to flag these as Errors because, during text modification, lines within these mark-ups are not modified in any way, and erroneous mark-ups will produce unpredictably erroneous results. It also flags (as merely Alerts, for information only) leading and double spaces (except within poetry/block-quote/sic mark-ups and in properly formatted "thought breaks"), since these can also be merged during text modification. Clicking on "Check Text" enables the "Modify Text" command button.

ERRORS/ALERTS

You should keep running the Check-Text function and correct all Errors that it flags before running "Modify Text". Alerts, however, are for information only, indicating some of the things that will be changed by the Modify Text function, and can be safely ignored. Note that lines alerted as having leading blanks might indicate missing poetry or other markups.

MODIFY TEXT

This function mainly serves to divide long lines of text to fit within the specificed column width. However, those parts of the text set off by Poetry mark-up (/*...*/), Block-Quote mark-up (/#...#/), and Stet/Sic mark-up (/$...$/) are not affected or modified in any way. Set the maximum line length in the appropriate textbox.

Optionally, very short lines of text may be joined (appended) to previous lines. Again, text within Poetry, Block-Quote, and Stet/Sic mark-ups is not affected. Set the maximum length of lines to be joined in the associated textbox. However, lines will not be joined if the resulting length would be greater than that specified  for dividing long lines above. The purpose of this feature is to reduce the amount of scrolling needed in further editing of the file.

Optionally, trailing blanks can be removed and double blanks can be merged. Again, text within mark-ups is never affected.

Also optionally, blank lines at the bottom of each page can be removed. (This can be a time-saver.)

Poetry and other mark-ups having extra characters, e.g.,
/* poetry
are flagged by the Modify-Text function and can be cleaned up (extra characters deleted) at the user's option. Also, "interior" poetry mark-up lines (used where poetry continues over page breaks) of the form "*/*", can be removed, also at the user's option.

"Naked" hyphens and dashes at the beginnings and ends of lines can be automatically "dressed": words are moved around across lines of text so that the dash or hyphen joins two words. Optionally, those that cannot be so dressed can be flagged with a character (or characters) specified in the associated textbox. If only flagging is selecting (but not dressing), all naked hyphens and dashes will be merely flagged. The default is not to dress them, but merely to flag them.

Abbreviations consisting of initials may have intervening spaces removed. For example:
e. g. --> e.g.
T. S. Eliot --> T.S. Eliot
U. S. A. --> U.S.A.
All combinations of upper-case letters are handled but otherwise only "i.e." and "e.g."

"AE", "ae", "OE", and "oe" ligatures may be split. The "OE", and "oe" ligatures, which are not in the Latin-1 character set and therefore not accepted by Project Gutenberg, should be split. However, the "AE" and "ae" ligatures are optional, at the discretion of the Project Manager; the default is not to split them.

Some of the changes made by GutSweeper are logged in a file named GSlog.txt.

It is recommended that GutSweeper be run with all the default options selected. Be sure to run the Check Text function first to ensure that no errors will occur because of mis-matched mark-ups. (Alerts, but not errors, can safely be ignored, but be aware that alerts of lines with leading blanks may be due to missing markups.)

Address all comments to BillFlis through the Distributed Proofreaders Forum or via email at flis@detk.com.