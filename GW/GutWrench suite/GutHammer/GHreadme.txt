This is the ReadMe file for GutHammer v. 0.6, a Windows-based tool to aid in post-processing of e-book texts at Distributed Proofreaders (DP). The main function of GutHammer is rewrapping the text to conform to a maximum desired column width. Thanks to dkretz for the original re-wrap code.

The latest version of GutHammer is always available as part of the zipped GutWrench download file at:
http://www.pgdp.net/tools/GW.zip

NEW IN THIS RELEASE (0.6.3)

--Long lines of poetry get re-wrapped with an indent of ten spaces.

NEW IN THIS VERSION (0.6)

--Previously indented text outside any mark-ups can be left as is (useful mainly for re-wrapping already re-wrapped texts).

NEW IN VERSION 0.5

--Poetry within /*...*/ mark-ups can be indented either by a fixed number of spaces (as before) or by the current indent plus the specified number of spaces.
--Bold text within <b>...</b> mark-ups can optionally be automatically converted to ALL UPPER CASE.

NEW IN VERSION 0.4

--Corrected a rarely occurring bug in the text-rewrapping function.
--Added a capability to open files in other folders (Open command under the File menu).

NEW IN VERSION 0.3

--Italic and bold mark-ups can be replaced by any desired string.
--Optionally, bold mark-ups can be left in (same as italics).
--Current settings can be saved as defaults.

NEW IN VERSION 0.2

--Corrected error in counting numbers of italics mark-ups replaced.
--Added logic to yield a smoother right-hand margin in rewrapped text.


INSTRUCTIONS FOR USE

The e-book file must reside in the same Windows directory (folder) as the GutHammer.exe file. The e-book file must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left. Then select which operations you would like to perform.


CHECK TEXT

The "Check Text" function displays messages in the field at the right of the GutHammer window; these are also recorded in an output text file, named GHerrors.txt.

Its main purpose is to check for unmatched and nested poetry /*..*/, block-quote /#..#/, and stet/sic /$..$/ markups, but it also flags double spaces (except within poetry/block-quote/sic mark-ups and in properly formatted "thought breaks").


REWRAP TEXT

This function rewraps the text, indents those parts set off by Poetry mark-up (/*...*/), rewraps and indents text within Block-Quote mark-up (/#...#/), and does nothing to text within Stet/Sic mark-up (/$...$/). Set the maximum line length and indent lengths in the appropriate textboxes. This also removes the mark-ups, trailing blanks, and any Page Separators still present in the file, and replaces series of multiple blanks by a single blank (except within Poetry and Stet/Sic mark-ups).

Optionally, italics mark-ups (<i>...</i>) are simultaneously replaced by any specified character or string of characters (the standard is underlines). If they are not replaced, they are each counted as a single character in adjusting the column width in rewrapped text.

Also optionally, bold mark-ups may either be left in or be replaced by any character or string of characters. If they are left in, they are counted as having no length in adjusting the column width of rewrapped text.

Within Poetry mark-up (/*...*/), text may be indented in either of two modes, Fixed or Additive. If the "Fixed" radio button is selected, each line of text is indented by the number of spaces specified. It does not matter whether the original text is indented or not; the specified indent is enforced absolutely. Note that the resulting indent is uniformly fixed at the value you specify! Any indents in the original are over-ridden, so do not use this where variable indents are desired.

If "Add" is selected (Additive indent mode), each line of text will be indented by its previous indentation plus the specified number of spaces. Thus, if a line is indented 3 spaces in the original, and an additive indent of 2 spaces is specified, then it will have an indent of 3 + 2 = 5 spaces in the output. Use this option (or use Stet/Sic mark-ups, described below) for poetry having variable indents. For simplicity, set up all poetry in the original so that the leftmost lines of text have no indent, and other lines have the proper relative indents (this conforms to the current DP Proofing Guidelines).

Within Block-Quote mark-up (/#...#/), text is both indented uniformly on the left by the number of spaces specified and rewrapped to fit the specified maximum line length on the right.

Within Stet/Sic mark-up (/$...$/), text is left as is, neither indented nor rewrapped. Use this around tables and around poetry with variable indentation.

Optionally, portions of the text that have already been indented can be left as is. (This is intended mainly for PPV use.) Select "Stet text outside mark-ups if already indented." This is useful for re-wrapping a previously re-wrapped text from which the mark-ups have been removed. Any remaining Poetry, Block-Quote, or Stet/Sic mark-ups are respected, but any other text that is indented at least one space will not be altered. 

Three cautions in using this option:
1) Mixing up indented and unindented text lines within the same paragraph (i.e., not separated by blank lines) will produce poor results.
2) Be careful to add indents or stet mark-ups to any unindented text (such as tables) that you do not want to be re-wrapped.
3) To re-wrap indented block quotes, you must re-insert the block quote mark-ups /#...#/.

The output file containing the rewrapped text is named GHout.txt. The original file is never changed.


SETTINGS MENU

The settings menu can be used to save the current settings as defaults to be used in future runs of GutHammer. Select "Save Defaults" to save the current settings. Select "Use Defaults" to restore the current settings to the last saved default values. These settings are stored in a file named "GHsettings.txt" which resides in the same Windows directory as the GutHammer application. If this file does not reside there (or does not exist), a warning will be issued and built-in settings will be adopted. Then selecting "Save Defaults" will create a new GHsettings.txt file, using the current settings selected on the GutHammer window.

This tool is sufficient for books with not too much special formatting (only poetry, tables, and block quotes, but no nesting of mark-ups); you will then have to set up the indentation for any specially formatted sections by hand (either before rewrapping within Stet/Sic mark-up or after rewrapping). For more complicated books, Big_Bill's RewrapIndent tool is recommended. Both of these tools also delete trailing blanks and poetry markup. (DO NOT use PRTK's Rewrap Text function! It will introduce errors into your text.) After using either one, I quite fussily follow with some manual smoothing of the right margin, also visually checking that abbreviations and such are not split across lines.

Address all comments to BillFlis through the DP Forum or via email at flis@detk.com.