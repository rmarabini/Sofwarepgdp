This is the ReadMe file for GutJack v. 0.1.0, a Windows-based tool to aid in preparing HTML versions of e-book texts at Distributed Proofreaders. Its purpose is to add some of the markups needed to make an HTML version. It is intended to be run at some point before the GutCutter tool; however, its use is completely optional and most of its features are compatible with other post-processing tools. GutJack searches for isolated lines of text (between blank lines) so that the user can decide whether to add HTML heading markups (e.g., <h1>...</h1>) and other markups.

The latest version of GutJack is always available in the GutWrench download at:
http://www.pgdp.net/tools/GW.zip

INSTRUCTIONS FOR USE

GutJack takes as input a text file and aids in preparing a "well-marked-up version," which is a text that has been readied for PPing at DP, with the addition of a few additional markups (mostly HTML). GutJack helps to add three types of HTML and shorthand markups including:
--HTML Header tags: <h1>...</h1>, etc.
--HTML centering tags: <center>...</center>
--Shorthand tag for "author" markup: >>Authorname (this is used by GutCutter to right-justify the following text, here "Authorname").
The file must reside in the same Windows directory (folder) as the GutVise.exe file and must have a text-file suffix, of the form *.txt.

To begin, select the e-book text from the input-file menu at upper left, then click the "Go" button. GutVise then scans the text down to the first isolated line of text (between blank lines), which it displays within its context in the text box. The user may then either add markups to this line or skip to the next such line.

To add markups, click on the appropriate button. For example, clicking "h1" adds <h1>...</h1> heading markups around the current line.

The ">>" button adds ">>" to the beginning of the current line. For several of its styles (notably Punch, IWM, Lippincott's, Notes & Queries, Mirror, and My Style), GutCutter will convert this into "author"-class markup in the HTML version, which results in this line being right-justified (up against the right margin).

Click the Revert button to restore the current line to its original state.

The usual Windows keyboard shortcuts are available. For example, note that the "1" on the "h1" button is underlined. This indicates that typing Alt-1 (hold down the Alt key while typing a "1") does the same thing as clicking this button. Most of the other buttons also have underlined characters to operate them.

Address all comments to BillFlis through the Distributed Proofreaders Forum or via email to flis@detk.com.