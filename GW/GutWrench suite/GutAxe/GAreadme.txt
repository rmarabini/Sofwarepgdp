This is the ReadMe file for GutAxe v. 0.6, a Windows-based tool to aid in pre- and post-processing of e-book texts at Distributed Proofreaders. Its purpose is to make rapid corrections of common errors encountered in OCRed e-texts, but it can also be used to make a quick scan of a text for Post-Proofing Verification (PPV). The errors GutAxe handles include (some) Stealth Scannos, words that are usually hyphenated or have accents or ligatures, and errors in punctuation and markups. It is intended mainly as a quick-and-dirty time-saving and error-reducing tool, and is not a replacement for other more effective tools, such as Gutcheck and a spell-checker.

The latest version of GutAxe is always available at:
http://www.pgdp.net/tools/GW.zip


NEW IN THIS VERSION (0.6)

--"Ignore All" button


NEW IN VERSION 0.5

--Handles regular expressions in plug-in files


NEW IN VERSION 0.4

--Simplified interface (de-emphasizes the optional text-checking function)
--Warnings and accepted changes are tabulated by Page Number


NEW IN VERSION 0.3

--Ligatures (ae and AE) are handled separately (Ligature menu)
--New format for plug-in files ("string" and "word" styles of changes)
--Added a Reload button to re-read the selected input file


NEW IN VERSION 0.2

--Brief explanations accompany each error/correction combination
--Expert mode is now functional (Default = On)


INSTRUCTIONS FOR USE

The e-book file must reside in the same Windows directory (folder) as the GutAxe.exe file and sub-directory GAplugins, which contains the 5 GutAxe auxiliary files: GAaccent.txt, GAaelig.txt, GAscanno.txt, GAmarkup.txt, and GAothers.txt. The e-book file must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left. Then select which operations you would like to perform from among the check-box choices.

For Post-Proofing, use the default settings:
--All Correction Modes turned on.
--"Check text only" turned off.
--New users may want to turn "Expert Mode" off.

For Post-Proofing Verification (PPV), use these settings:
--"Check text only" turned on.
--"Expert mode" turned on (default).

In actually using it for PPV, I recommend reading (e.g., in Notepad) through the file GAerrors.txt. Real errors can be copied into the PPV Report Card for giving feedback to the PPer. Note, however, that to reduce the amount of output, GutAxe reports only the first suspected error on each line of text; this may or may not reflect the nature of the actual error. Thus, it is a good idea to include a brief explanation of the actual error after the line of GutAxe output.

"GO" BUTTON

The "Go" function searches the text for (highly) likely errors and displays each in its context with a suggested correction. The user may then:
--accept the correction by clicking "Change",
--reject it by clicking "Ignore", or
--stop checking for the current suggested change by clicking "Ignore All", or
--abort the entire process by clicking "Cancel".
This function produces an output text file, named GAout.txt, with the accepted changes. The input file is never modified. The accepted and rejected changes are also logged in file GAlog.txt; they are also tabulated by Page Number (provided DP-style Page Separators are present in the file).

If "Check Text Only" is checked, possible errors are displayed in the field at the right of the GutAxe window; these are also recorded in an output text file, named GAerrors.txt (unless Record Mode is turned off). This is for information only, and it is not necessary to check the text before modifying it (but see HOW I USE IT below).

If GutAxe finds an actual error in the text but does not offer the appropriate correction, make a note of the line number and correct it by hand later. Or, after completing the text-modification pass, re-run it with "Check Text Only" checked to find that error again.


MODES MENU

--Expert Mode (Default = On) requests fewer and briefer messages.
--Silent Mode requests fewer warning beeps.
--Record Mode causes error messages to be saved in external text files. The default is Record Mode = On; turning it Off prevents these files from being created or written over. 


CORRECTIONS MENU

This menu selects which changes GutAxe will try to make to the input file.

For best results, set all selections to Checked (default).


LIGATURE MENU

Use of "ae" ligatures is optional. This menu provides control of whether GutAxe tries to correct these and how.

--Don't check ae's: no occurrences of "ae" will be flagged for possible changing to a ligature.
--Use plug-in file: only strings defined in the file GAaelig.txt will be searched for in the file.
--Check all ae's: every occurrence of the letter combination "ae" (lower- and upper-case) will be referred to the user for possible changing to the appropriate lower- or upper-case ligature.


THE PLUG-IN FILES

GutAxe is accompanied by five auxiliary files, GAaccent.txt, GAaelig.txt, GAscanno.txt, GAmarkup.txt, and GAothers.txt. Each contains a list of potential corrections or "rules", in this format: search type (as string, word, or regular expression), the text (error) to be searched for, the likely correction, and a description (each separated by a delimiting character, such as a backslash "\"). Errors are searched for as "words", as "strings", or as "regular expressions", as defined by the first field of each line of any of these files: "s" = string, "w" = word, "r" = regular expression. 

The difference is the way that GutAxe uses them. "Word" errors are searched for as entire words, surrounded by blanks or punctuation. Thus, in applying the rule "w\hut\but\h/b confusion", GutAxe searches for the word "hut", standing alone, but not for the string "hut" within another word, such as "huts" or "shut"; if it finds the word "hut", it suggests "but" as its replacement and gives "h/b confusion" as the description.

"String" errors, on the other hand, are searched for as character strings. For "s\hotel\hôtel\circumflex", GutAxe finds not only "hotel" but also "hotelier", and suggests "hôtel" as the replacement for the "hotel" within "hotelier" to make "hôtelier". This approach allows a single rule to handle compound, feminine, plural, capitalized, and other variants of a base word or part-word.

"Regular expressions" are also searched, indicated by a leading "r" in the rule. For more details on these, see the DP Forum. Since the backslash "\" often appears in regular expressions, GutAxe uses a flexible system for establishing the delimiter between the several fields. Specifically, it takes the second character of the rule as the delimiter. Convenient choices for delimiters between regular expressions include the low-line character "_" and the tilde "~". Thus the rule "r_tbi_thi_b/h confusion" converts every occurrence of the string "tbi" to "thi", because of "b/h confusion". The advantage of regular expressions is their power to handle a large number of cases with a single rule.


HOW TO USE IT

GutAxe may be used to correct a text at any stage of pre- or post-processing. Since it is designed to return a low percentage of false positives and to quickly and efficiently make corrections, it is recommended that it be run early on during either of these stages. (GutAxe does not try to make changes to  DP-style Page Separators.) A good plan to begin post-processing is as follows:

1. Run GutSweeper with all options selected: first Check Text and make corrections by hand until it finds no more Errors; then Modify Text.

2. Run GutAxe with "Check Text Only" checked. Make a mental or written note of the kinds of errors it reports. (It also saves these in a file, GAerrors.txt.)

3. First editing pass: As you do this, decide which of GutAxe's reported errors (especially hyphenation and spelling variants, such as "today/to-day" and "Caesar/Cæsar") should be accepted. 

4. Run GutAxe again with "Check Text Only" unchecked.

5. Continue post-procesing ....

However, GutAxe's "Check Text Only" feature is purely optional. It is quite safe to run GutAxe to make corrections without first checking the text.


CONTACT INFO

Address all comments to BillFlis through the Distributed Proofreaders Forum or via email at flis@detk.com.

