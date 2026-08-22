# iush

**"VIRTUALIZE" IN YOUR BROWSER! https://iamdominic2.github.io/iush/**

Scratch link: https://scratch.mit.edu/projects/1369594616/ (Due to technical limitations, use `[` for Backspace, `]` for Shift, and `^` for Ctrl on Scratch.)

It stands for ***i***nteractive ***u***ser ***sh***ell, in honor of my best friend at school Aayush.<BR>
Command-line emulator built from scratch in Scratch - stretching it to the limits and scratching my head over why anyone would actually (*except me*) bother to do this.

Supported commands:<BR>
`cd [directory]`: Change your working directory<BR>
`pwd`: Output your working directory<BR>
`c:`: Change your working directory to the `c:` root<BR>
`dir [directory]`: List **all** files and subdirectories in the directory<BR>
`md [name]`: Makes a new directory with your selected name.<BR>
`del [file]`: Deletes a file (not a directory)<BR>
`rd [directory]`: Removes an empty directory. Use `rd /s [directory]` to remove a non-empty directory (**and all files and subdirectories in the directory**)<BR>
`set [file] [text]`: Changes the file's data to the text string you input<BR>
`echo [text]`: Outputs the text back to you<BR>
`write [text or file]`: Outputs text back to you; however, if you input an existing file path, it outputs the file's contents back to you<BR>
`copy [file] [new path]`: Copies a file to the new path (the original will not be erased)<BR>
`cls`: Clears the screen - especially useful when it's too bloated or laggy!<BR>
`date`: Outputs the date in DAYOFWEEK DD/MM/YYYY format. E.g. Monday 17/8/2026.<BR>
`time`: Outputs the 24-hour current time in HH:MM:SS. For instance, 20:25:19.<BR>
`color [hex]`: Changes the color of the text (6-digit hex; if it becomes black due to a typo of an invalid command or an input of `000000`, blind-type something like `color ffffff` and it would fix itself) <BR>
`help`: Gives a list of commands, from `c:\iush\help\.txt`<BR>
`help [command]`: Gives help with the command, from `c:\iush\help\[COMMANDNAME].txt`<BR>
`find [string]`: Searches for a file or directory with a string in its name.<BR>
`exit`: Exits the terminal.<BR>

Built-in programs or scripts (Type the full path in the terminal to execute it! You can even write your own with `set` or `Notepad.exe`. <BR>
c:\program\matrixrain.exe<BR>
![MatrixRain](screenshots/matrixrain.png)
c:\program\notepad.exe (Command: `Notepad [optional: file]` )<BR>
c:\program\paint.exe (Command: `Paint [optional: file]` )<BR>
c:\program\regedit.exe (Command: `Regedit`)<BR>

*Alternative drives are not supported (for now)*
 
### Command line basics
1. No news is good news! Rather, it's like a teacher - if the shell starts talking back to you, you know you've done something wrong.
2. Use the mouse to copy text (your clipboard will be shown in the square brackets \[\] at the bottom of the page), and Ctrl+V to paste it back! (*Note that Ctrl+C **aborts** the currently running command, and the mouse does NOT move the cursor position)
3. Use `&` to chain commands together!
4. (*Unique to iush*) However, if you want to **literally** have "&", for instance, when using `set` in a file to execute as a batch later, add `#LITERAL&` (**exact phrasing**) to the end of your command.

#### A catastrophic? bug
After executing `rd /s c:\`, I discovered something horrifying: only half of all my files were erased! I then made a shocking discovery: Though successfully removing a file erases it from the list, the `Counter` for the file check still increased by 1 even though all other values would move 1 backward, causing it to miss the immediate next file. This has since been fixed.

## Domemory
![Presentation](screenshots/presentation.png)
Classic spaced repetition active recall - Maybe the first of its kind on Scratch! For students and learners alike, if you are too lazy to install Anki, you can do it straight from the Browser!

* Pre-trained SuperMemo 5 spaced repetition algorithm (SuperMemo 2 was too boring to code!) - with bilinear interpolation of the Absolute Factors (`AF`) (also known as Ease Factor or Ease in some other spaced repeititon apps)
* No modern corporate "gamification" bloat - focus purely on the pragmatism of self-testing!
* Cherish the wisdom of your new knowledge! <BR>
* SM-5 optimal factor matrix derived from about 19,000 repetitions of me using SuperMemo itself:<BR>
![OF-Matrix](screenshots/12406.jpg)

#### Bug fixes of Domemory
1.1: Wrong linear interpolation bug fixed, freeze on G + Item #0 (underflow bug) fixed<BR>
1.2: Undesirable registration of "q" and "a" into text fields when using them as quick triggers to edit fixed.<BR>
1.3: Integration into iush, with a command to exit;  remapped some keybinds like Delete to "-" to account for the fact that some keyboards don't have such physical keys; fixed broken Optimal-factor matrix

***Note: Domemory save data is stored separately from the file system, and is only lost on Reload.***

## Notepad
![Notepad](screenshots/notepad.png)
A text editor. The good thing about this is that you can make new lines, unlike the terminal's "set" command. Theoretically, this would allow for multiple `set` commands with `#LITERAL&` (since, for now, you can't have both literal and separator & on the same line)

Try this command to see the example text file: `notepad c:\readme.txt`

The keyboard shortcuts are chosen specifically to not clash with the browser. I originally planned *Ctrl+Shift+A* for **Save As**; however, Chrome recently added a "Search tabs" option that has this exact shortcut, so I remapped it to Ctrl+A. Sorry if it breaks your muscle memory; please forgive me *lol*

## Paint
![Paint](screenshots/paint.png)
A painting program with 22 different colors. I learned how to convert color data to text, as it saves as English letters: `0` for black, `a`-`u` for colors! 

Note that to prevent massive file sizes and extreme lag (Scratch engine has to re-render it every frame!), I had to make the pixels somewhat big; however, it is still usable to an extent. 

***AHA! Moment***: If you hate the fact that it's in `terminal black`, and would like it to look more "light mode" paper candy, a single keystroke of W will do the trick!

## Regedit
![Regedit](screenshots/regedit.png)
A program allowing you to edit the name and data of registry members. In other operating systems, the file system is quite abstracted from the registry; however, in this one, it is combined into one: the **`Name`** and the **`Data`**.

***WARNING***: There is no telling what would happen if you mess up a Name or a Value. (You might have to reload the page.) Better to `Export` the Registry Member Lists just to be on the safe side. (More on that later.)

### Experiment!
Opening text files in Paint will result in some weird colors due to the bitmap conversion, and vice versa.

## Importing & Exporting
I cannot force the browser to download files to your computer, so if you want to save, type in `regedit`, and right click -> Export **BOTH** the `Name` and `Data` lists. When you reload, type in `regedit` again and right-click -> Import **BOTH** the lists correspondingly.<BR>
Again, **NOTE THAT** Domemory save data is **separate**.  It was originally a separate program of mine, but I realized it had a terminal-type vibe, so I re-added it here so you can do your repetitions with an operating system emulator.

## Example
<img width="782" height="572" alt="2222" src="https://github.com/user-attachments/assets/fce4f786-534c-4759-8d8e-721acb61115c" />

#### Have fun with `iush`, and I hope it can cure your terminal *terminal* anxiety (if you had it)! : )

