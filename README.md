# TinTin++ client scripts for ArcticMUD
Welcome to Arctic and enjoy your stay.

### Table of Contents
- [Introduction](README.md#Introduction)
- [Initial setup for WinTin++ (Windows)](README.md#How-to-use-WinTin)
- [Playing with WinTin++](README.md#Playing-with-WinTin)
- [Controlling multiple characters with WinTin++](README.md#controlling-multiple-characters-with-wintin)
- [Setup for TinTin++ (Mac/Linux)](README.md#tintin-users-tintin-on-maclinux)
- [Logging](README.md#Logging)

# Introduction
Arctic has now been updated to use full ANSI coloring. TinTin++ and JMC are
the recommended MUD clients of choice as they support extended colours.
Instructions for using JMC are available in a separate repository.

Within this package, you will find comments on what the cause is for each
highlight, trigger, and substitution. Please review these messages as they 
will help you along your adventure.

Within the Arctic_Aliases file, each class with spellcasting ability has
aliases already created. You should find these aliases at the very least 
somewhat intuitive and easy to work with. Become familiar with these aliases
to better hone your skills and more comfortable with your chosen class!

If you are playing a class that has the ability to 'refresh' others, there is
an auto-refresh trigger included in this package which is triggered when other
characters use the "pant" emote, but it is commented out as the action the 
trigger takes depends on your class. If you play a class that can make use of 
this trigger and you would like to have it enabled, remove the #nop comment 
from the appropriate line in the TT_Arctic_Actions file.

# How to use WinTin++
### WinTin++ First-time setup:
### WARNING If you are already using WinTin++, this will replace your current setup.

1.  Unzip this file pack to your default WinTin++ folder
2.  Right click the "tt++" Application in the folder
3.  Mouse over Send To
4.  Click Desktop (Create Shortcut)
5.  Repeat steps 2, 3, and 4
6.  Browse to your desktop
7.  Left click one of the two tt++ shortcuts
8.  Press your F2 key
9. Name the file ArcticMUD 1
10. Repeat steps 7 and 8
11. Name the second file ArcticMUD 2
12. Right click ArcticMUD 1
13. Click Properties
14. Press End (above your arrow keys)
15. Press Space Bar
16. Enter: -r TT_Win1
17. Click OK
18. Right click ArcticMUD 2
19. Click Properties
20. Press End (above your arrow keys)
21. Press Space Bar
22. Enter: -r TT_Win2
23. Click OK
24. Optional: you can move the shortcuts to your Desktop or somewhere else

# Playing with WinTin++
1. Double click ArcticMUD 2 (important: do this before opening Window 1!)
2. Double click ArcticMUD 1  

When you first log in to Arctic with a character enter `#read Options_Prompts.txt`
to load the default options and prompts that most players enjoy.  This only needs
to be done once per character.

If your session ever disconnects, you have one of two options:

* Option 1
    1. Close all TT++ Windows
    2. Reopen your TT++ Windows as per the instructions above

* Option 2
    1. Enter `#session Arctic mud.arctic.org 2700 Arctic` into whichever screen has
       disconnected

# Controlling multiple characters with WinTin++
With the setup provided, you're able to control both windows by typing into one.
There are three different scenarios in which you can input commands.
These are:
   1) Type normal text or a command
      - This will send the command to your first window
   2) Start your command with "y" (not including the quotation marks)
      - This will send the command to your second window
   3) Start your command with "v" (not including the quotation marks)
      - This will send the commands to both windows

Examples:
```
say Hello sir!
Window says "Hello sir!"
```

```
y say How are you today?
Window 2 says "How are you today?"
```

```
v say I'm doing fine, thanks.
Window 1 AND Window 2 say "I'm doing fine, thanks."
```

# TinTin++ users (TinTin++ on Mac/Linux):

1. Open two terminal sessions.
2. In the first session, start Tintin++ and type `#read TT_Win2`, then login with your alt.
3. In the second session, start Tintin++ and type `#read TT_Win1`, then login with your main character.

# Creating your own triggers, aliases, highlights, and substitutions

SYNTAX:
|Alias|#alias  {keyword} {output text}|
|-----|-------------------------------|
|Example|#alias  {mm} {cast 'magic missile'}|

|Trigger|#action {line to trigger} {what you want to do}|
|-------|-----------------------------------------------|
|Example|#action {^There were %0 coins.}  {get all.coins corpse}|

|Substitutions|#sub {line to substitute} {replacement message}|
|-------------|-----------------------------------------------|
|Example|#sub {You eat some bread} {You eat some gnome.}|


|Highlights|#highlight {Line to highlight} {color}|
|----------|--------------------------------------|
|Example|#highlight {You have been blinded! %1} {cyan}|

If there are aliases, triggers, substitutions, or highlights you do NOT
want to keep, whether they're your own, or those included in this package,
you can use #unalias, #unaction, #unsub, and #unhighlight respectively.

If you already have a text file with subs you would like to import:
1) Place the file in the /bin sub folder of your WinTin++ folder
	or within the directory that contains the tt++ binary on MacOS/Linux
2) Enter: #read FILENAME once the package has been run and Window 1 and
   Window 2 are operational

If you would like to create your own, I would highly recommend, as does the
developer of TT++, you append the files themselves with any updates.

The file names are:
   - TINTIN_Arctic_Highlights_Subs.txt
   - TINTIN_Arctic_Actions.txt
   - Arctic_Aliases

# Logging

It is highly advisable for Windows users to use plain logging. Raw logging is
set by default and is more difficult to view. Steps will be provided below for
those who wish to log in raw (ANSI color) data.

```
#config log plain
#log append FILENAME
```
Where FILENAME is the name of the log (your decision).
To end logging, use `#log off`

To view a plain log on Windows:
1) Browse to your WT++ default directory and move to the /bin folder.
2) Double click the log
3) Choose a Windows program, "Notepad"
4) Click "OK"

Raw (ANSI) logging:
Everyone's computer is different and it's impossible to take every scenario
into account. This short, basic step-by-step guide will show you how to read
your logs in ANSI in Windows 10. If you are a more advanced user, you can
leave the log files where they are saved and read them from there.

```
#config log raw
#log append FILENAME
```
Where FILENAME is the name of the log (your decision).
To end logging, use `#log off`

To view a RAW (ANSI) log on Windows 10:
1) Download Git Bash: https://git-scm.com/download/win
2) Follow the installation procedures
3) Click the Start Menu
4) Enter: Git Bash
5) Press Enter
6) Browse to your TT++'s /bin folder
7) Move the log file you wish to read to your Desktop
8) Enter:  
   For Windows 10 Basic:                      `cat ~/OneDrive/Desktop/FILENAME`  
   For Windows 10 Pro / Non-Onedrive Users:   `cat ~/Desktop/FILENAME`  

On \*NIX/MacOS you can just use `cat` to view the raw log.
