ExeRunner ReadMe File

Version of 17 Feb 2004

ExeRunner is a little GUI application that runs a DOS executable 
program (.exe) without opening a command-line interface (Command Prompt).

It runs the command:

> Program.exe Filename1 [>] [Filename2]

where both the ">" and the "Filename2" are optional.

Thus, it runs any of these combinations:
> Program.exe Filename1
> Program.exe Filename1 Filename2
> Program.exe Filename1 > Filename2

1. Copy ExeRunner to the same directory as the DOC executable and 
the files to appear in the command-line.
2. Launch ExeRunner (double-click it).
3. Select the program to be run in the left menu.
4. Select Filename1 from the middle menu.
5. Select Filename2 from the right menu, or select "None".
6. Optionally, select the "Insert >" checkbox. (Selecting "None" for 
Filename2 unchecks this.)
7. Click "Run".

If a file does not appear in the right-hand menu, it is possibly an 
Archive or Read-Only file (this is a little safety feature). If you want 
such a file to appear in this menu, first change its Properties in Windows.

WARNING: Some programs may overwrite Filename1; check that program's 
documentation, or make a copy before running.

Only .exe files will appear in the left menu.
