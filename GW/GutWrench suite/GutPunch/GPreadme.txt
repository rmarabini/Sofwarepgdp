This is the ReadMe file for GutPunch v. 0.2.0, a Windows-based tool to aid in preparing HTML versions of e-book texts at Distributed Proofreaders. Its purpose is to shift or re-sequence page numbers in DP-style Page Separators.

The latest version of GutPunch is always available in the GutWrench download at:
http://www.pgdp.net/tools/GW.zip


NEW IN THIS VERSION (0.2.0)

--Re-sequencing of Page Separators.


INSTRUCTIONS FOR USE

GutPunch takes as input a DP-style text version of an e-book as it comes out of proofing and into post-processing, that is, with its Page Separators intact.  GutPunch reads the e-book text file, modifies the Page Separators, and writes the result out to another file GPout.txt. The original file is never modified. The e-book file must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left, or select Open under the File menu.


CHECK PAGE SEPARATORS

This function reads the file and counts the Page Separators. Optionally (by checking "Show All"), the Page Separators are shown in the GutPunch window.


MODIFY PAGE SEPARATORS

This function modifies the numbers on the Page Separators by shifting them by a prescribed number, which may be positive or negative, or by re-sequencing them, starting at a prescribed number, which may also be positive or negative. These functions are useful when the page numbers in the scans do not match the numbers assigned to the scan files, and you plan on making a version (typically HTML) with correct page numbers. Optionally, the pages falling before actual page 1 may be renumbered with Roman numerals.

For example, suppose the original Page Separators look like this:

-----File: 001.png---\wdw531\audreyii\-------------------------------------
-----File: 002.png---\wdw531\audreyii\-------------------------------------
-----File: 003.png---\wdw531\audreyii\-------------------------------------
-----File: 004.png---\wdw531\audreyii\-------------------------------------
-----File: 005.png---\wdw531\tmeekins\-------------------------------------
-----File: 006.png---\khandy\delta\----------------------------------------
-----File: 007.png---\silvermane\delta\------------------------------------
-----File: 008.png---\silvermane\delta\------------------------------------
-----File: 009.png---\davidb715\delta\-------------------------------------
-----File: 010.png---\dmyod\delta\-----------------------------------------
-----File: 011.png---\dmyod\pauler2\---------------------------------------
-----File: 012.png---\davidb715\delta\-------------------------------------
-----File: 013.png---\dmyod\delta\-----------------------------------------
-----File: 014.png---\davidb715\pauler2\-----------------------------------
-----File: 015.png---\dmyod\pauler2\---------------------------------------

Suppose further that page 1 of the original book falls on scan page 010(.png), and that the page before that is numbered "vi". Then select "Shift numbers by", enter a shift of -9 (minus nine) in the text box, select "Use Roman numerals" and set "New page 0 = " to "vi" (without the quotes). Then on clicking "Modify", the modified Page Separators will come out looking like this: 

-----File:-8.png-----\wdw531\audreyii\-----
-----File:-7.png-----\wdw531\audreyii\-----
-----File:-6.png-----\wdw531\audreyii\-----
-----File: i.png-----\wdw531\audreyii\-----
-----File: ii.png-----\wdw531\tmeekins\-----
-----File: iii.png-----\khandy\delta\-----
-----File: iv.png-----\silvermane\delta\-----
-----File: v.png-----\silvermane\delta\-----
-----File: vi.png-----\davidb715\delta\-----
-----File: 1.png-----\dmyod\delta\-----
-----File: 2.png-----\dmyod\pauler2\-----
-----File: 3.png-----\davidb715\delta\-----
-----File: 4.png-----\dmyod\delta\-----
-----File: 5.png-----\davidb715\pauler2\-----
-----File: 6.png-----\dmyod\pauler2\-----

Note that the three pages before page "i" have negative numbers; these were probably not numbered in the original book. These Page Separators will need to be removed from the text file by hand (with an editor). If "Leave as negative" is selected, then the above pages numbered with Roman numerals would all have negative page numbers.

As a second example, suppose the original Page Separators look like the originals above, and the page numbers match the numbers on the Page Separators up to page 9, but skips to 12 on page 10. To make up for the gap, introduce two dummy Page Separators after 9; an easy way to do this is to just duplicate 9 twice:

-----File: 001.png---\wdw531\audreyii\-------------------------------------
-----File: 002.png---\wdw531\audreyii\-------------------------------------
-----File: 003.png---\wdw531\audreyii\-------------------------------------
-----File: 004.png---\wdw531\audreyii\-------------------------------------
-----File: 005.png---\wdw531\tmeekins\-------------------------------------
-----File: 006.png---\khandy\delta\----------------------------------------
-----File: 007.png---\silvermane\delta\------------------------------------
-----File: 008.png---\silvermane\delta\------------------------------------
-----File: 009.png---\davidb715\delta\-------------------------------------
-----File: 009.png---\davidb715\delta\-------------------------------------
-----File: 009.png---\davidb715\delta\-------------------------------------
-----File: 010.png---\dmyod\delta\-----------------------------------------
-----File: 011.png---\dmyod\pauler2\---------------------------------------
-----File: 012.png---\davidb715\delta\-------------------------------------
-----File: 013.png---\dmyod\delta\-----------------------------------------
-----File: 014.png---\davidb715\pauler2\-----------------------------------
-----File: 015.png---\dmyod\pauler2\---------------------------------------

Then select "Re-sequence from", and enter a starting page number of 1 in the text box. Then on clicking "Modify", the modified Page Separators will come out looking like this: 

-----File: 1.png---\wdw531\audreyii\-------------------------------------
-----File: 2.png---\wdw531\audreyii\-------------------------------------
-----File: 3.png---\wdw531\audreyii\-------------------------------------
-----File: 4.png---\wdw531\audreyii\-------------------------------------
-----File: 5.png---\wdw531\tmeekins\-------------------------------------
-----File: 6.png---\khandy\delta\----------------------------------------
-----File: 7.png---\silvermane\delta\------------------------------------
-----File: 8.png---\silvermane\delta\------------------------------------
-----File: 9.png---\davidb715\delta\-------------------------------------
-----File: 10.png---\davidb715\delta\-------------------------------------
-----File: 11.png---\davidb715\delta\-------------------------------------
-----File: 12.png---\dmyod\delta\-----------------------------------------
-----File: 13.png---\dmyod\pauler2\---------------------------------------
-----File: 14.png---\davidb715\delta\-------------------------------------
-----File: 15.png---\dmyod\delta\-----------------------------------------
-----File: 16.png---\davidb715\pauler2\-----------------------------------
-----File: 17.png---\dmyod\pauler2\---------------------------------------

Now remove the dummy Page Separators corresponding to the missing pages (10 and 11), and you are left with:

-----File: 1.png---\wdw531\audreyii\-------------------------------------
-----File: 2.png---\wdw531\audreyii\-------------------------------------
-----File: 3.png---\wdw531\audreyii\-------------------------------------
-----File: 4.png---\wdw531\audreyii\-------------------------------------
-----File: 5.png---\wdw531\tmeekins\-------------------------------------
-----File: 6.png---\khandy\delta\----------------------------------------
-----File: 7.png---\silvermane\delta\------------------------------------
-----File: 8.png---\silvermane\delta\------------------------------------
-----File: 9.png---\davidb715\delta\-------------------------------------
-----File: 12.png---\dmyod\delta\-----------------------------------------
-----File: 13.png---\dmyod\pauler2\---------------------------------------
-----File: 14.png---\davidb715\delta\-------------------------------------
-----File: 15.png---\dmyod\delta\-----------------------------------------
-----File: 16.png---\davidb715\pauler2\-----------------------------------
-----File: 17.png---\dmyod\pauler2\---------------------------------------

The Page Separators now match the book page numbers.

The re-sequencing starting number may also be negative, and Roman numerals may be requested for the non-positive page numbers, as described above for simple shifting.

Re-sequencing is also useful when the book has two or more columns, each scanned in a separate image. Remove the Page Separators that do not begin a new page (i.e., at the top of the second and later columns), then re-sequence.

The result is always output as GPout.txt. 

Address all comments to BillFlis through the Distributed Proofreaders Forum or via email to flis@detk.com.