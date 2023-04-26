# Introduction
Lazy Shell is a third party .NET application written in the C# programming language which is capable of editing a wide range of elements within the Super Mario RPG (US) ROM image file. 
**These elements include:** 
- allies 
- battle animations 
- attacks
- spells
- sound effects
- music
- battlefields
- dialogues
- fonts, effects
- events
- formations
- items
- shops
- level/location maps
- the main title
- menus
- the mine-cart
- maps
- monsters
- sprites
- world maps, and more. 
In addition, it also includes a help database and a project manager to help organize a full hack project.

# MAIN FEATURES
The editor is comprised of 17 individual editors. Various status editors include modification capabilities for
- the statuses of monsters
- formations
- formation packs 
- items 
- spells 
- attacks 
- shops 
- new game properties 
- level-ups 
- timing properties

## Monster Editor
Contains a battle script editor for each monster. 
## Level Editor
Allows the user to modify 
- maps of areas (aka locations) using a paint-like interface, 
- NPCs (ie the sprites in the maps), 
- exit fields (aka entrances), 
- event fields, 
- overlaps,
- basic layering properties.
## template creator/editor 
lets the user store a separate portion of the map composed of all 3 layers and the physical layer into a single file. 
## The scripts editors 
enable the user to modify the
- event scripts, 
- action scripts,
- animations scripts. 

**Commands within event scripts and action scripts may be**
- added
- modified
- deleted
- moved
- copied and pasted. 

**Commands within animation scripts may be**
- modified
- moved, or replaced with new commands of the same or smaller length

adding/deleting entirely new commands within animations is not supported and never will be due to the fickle and erratic nature of the animation script engine.

## The Sprites editor 
Able to modify a sprite's: graphics, palette and animations. 
## The effects editor 
Allows the user to edit spell effects and their respective graphics, palettes, and animations. 
## Dialogue editor
Allows the user to view and edit the dialogues (aka the game script) as well as the dialogues which appear in battles and the graphics of the dialogue background tiles. 

Fonts, font colors, and a new font generator will let the user create an entirely new font table based upon manual editing or a supportive font installed on the OS.
## The World Maps editor 
World maps, world map palettes, and the locations that appear on world maps can be modified. 
The logo banner graphics and palettes can be modified here as well.
## The Audio editor 
Able to export, import, clear, and playback the audio samples used by the SPC engine. 

The .wav files can be edited in a third party program such as Audacity. SPC data can be edited in a variety of ways, allowing the user to create entirely new pieces of music.

Instruments can be changed as well as well as the raw SPC track data, which can even import custom scripts from a text document.
## The mini-games editor 
Can modify the minecart mini game maps for all four stages and the objects in the same manner as levels. 
## The menus editor 
Allows the user to modify the menu palettes and import an external image into the menu backgrounds, as well as import an image into the frame image.

# EXTRA FEATURES
Some portions of the editor have tooltips for almost every single control. 
**Just press F1 (or click the ? buttons found in most editors) and move the mouse over a control** to see what that property is for.

There is also a conversion tooltip for showing the hexadecimal or decimal value for the value in the
control when moving the mouse cursor over it. 
**Press F2 to enable this feature, or click the base conversion button found in most editors.** 

Users are also able to import and export many elements from previously exported .dat, .bin, or .pal files in all portions of the editor as a means of backing up or inter-changing elements. 

Clearing/erasing data is managed as well so as to free up space for new scripts or dialogues.

The notes database manager was written for the editor to aid the user aiming to create a full or partial hack. 

Indexes for elements such as monsters, levels, etc. can be added and a user-defined description
provided as well. 

Adding new indexes is simplified with an option for adding a specific index within a portion of the editor by right-clicking the name list or index number. 
The user can also load a selected index in the notes database manager into its respective portion of the editor where it can be modified there.

The patch feature reads a list of patches from the currently defined patch server http:// or ftp:// location and can apply those patches to the currently loaded ROM image.

A previewer for levels, event scripts and battle scripts lets the user load a temporary ROM created from the current modifications in the currently loaded ROM image into an emulator of choice (the only options
so far are ZSNES and SNES9X). 

Lazy Shell will create a save state which, when loaded, will immediately enter the current level or initiate the current event or battle script.

There are many more smaller features which are too numerous to list here, and are scattered throughout the editor with the purpose of easing the use of Lazy Shell and reducing the amount of work required
to complete a task.

That's what all of these extra features are here for. Not as bells and whistles, but for making the hacking process less headache-inducing.

# UNSUPPORTED FEATURES
Lazy Shell can NOT edit the new game intro sequence and graphics, the end credits graphics, or end credits fonts. 

It cannot make any changes to 65c816 assembly code in the ROM image (with some small exceptions).

Additionally, ROM expansion is also not supported by the application due to the complications of the SA-1 chip in the game's engine.

# USING THE PREVIEWER
**Before using the previewer, do the following: **

1. Make sure all editor files are in the same folder. 
2. Configure the emulator's save-state folder to read/write to the same folder as any loaded ROM. ZSNES 
		by default already does this, and so does Snes9x v1.43. However, later versions of Snes9x will by default read/write to a "Save" folder created within the emulator's main folder, and if not changed it will fail to load the preview save state.

Choose either the SNES9X or ZSNES emulator file to use when opening the previewer. 

ZSNES will automatically load the generated save state when the emulator is loaded from the previewer, but for SNES9X the F1 key must be pressed manually to load the generated save state. 

If the emulator has problems loading the save state, make sure the 2 steps above have been completed. 
The latest version of ZSNES (v1.51 as of this release) is supported.
Snes9x v1.43 and/or its derivatives (rerecord, Geiger's debugger, etc.) are preferred and should work. 

# IMPORTING CUSTOM WAVS
Follow these steps to successfully import a .WAV file of your choosing. Say you have a .WAV file, "MyWavFile.wav", that you wish to replace one of the samples in this audio editor with. 
**Here are the steps you need to take: **
1. Download and install Audacity, a good free audio editing program.
     http://audacity.sourceforge.net/download/
2. In the Lazy Shell audio editor, export any sample to a file named "OldSample.wav".
3. Open "MyWavFile.wav" into Audacity.
4. While in Audacity, copy the audio data (Ctrl+A, Ctrl+C). Close Audacity.
5. Open "OldSample.wav" into Audacity.
6. While in Audacity, paste the copied audio data over the old data (Ctrl+A, Ctrl+V).
7. Export to a .WAV file named "NewSample.wav".
8. In the Lazy Shell audio editor, import "NewSample.wav".

**MAKE SURE THE SELECTED Hz SAMPLE RATE IS THE SAME AS THE IMPORTED .WAV FILE**
	The reason this is the only way to do it is because by using the same exported file ("OldSample.wav") with the modified WAV data from "MyWavFile.wav", it retains some obscure data from "OldSample.wav" in "NewSample.wav" which is necessary to have in order to successfully import a .WAV file.


# FILES IN ARCHIVE
**Make sure all files stay within the same directory as each other, or there will be problems running Lazy Shell**
- **LAZYSHELL.exe**
	The application.
 
- **Lunar Compress.dll**
	Generates automatically when needed. This file is essential to Lazy Shell's functionality. It decompresses and compresses the data that Lazy Shell modifies. 
	
	It is needed to run the Stats, Levels, and Sprites editors and **must be in the exact same directory as LAZYSHELL.exe** Without it, the program is almost completely functionless.
 
- **RomPreviewBaseSave.000 and RomPreviewBaseSave.zst**
	These generate automatically when needed. Base savestates for SNES9X and ZSNES, respectively.
		 These are needed for previewing levels, event scripts, and battle scripts using either ZSNES or SNES9X. 
	To avoid complications, make sure the emulators are in the same directory as everything else and that their save directories are configured likewise.
- **changes.txt**
	All of the fixes, modifications, and additions since the earliest versions are chronicled here.
- **readme.txt**
	This file.

# BUGS, ERRORS, EXCEPTIONS AND COMPLICATIONS IN FUNCTIONALITY.

The editor may occasionally crash or not function properly due to certain errors in the code. 

Please remember that this is almost certainly the programmer's fault and NOT yours, the user's. As often is the case, when an error surfaces or the program behaves in a buggy fashion, the user tends to immediately feel that they are to blame or the programmer is blaming them for the error. This is not correct: almost all of the time, it's the programmer's fault. 

Incidences when it might be the fault of the user may be due to a corrupt ROM being loaded (a corrupt ROM basically means any SMRPG rom which has been modified in any way, shape or form). 
	This includes a ROM edited by Lazy Shell, but errors may occur if a ROM has been modified outside of Lazy Shell (ie. a hex editor),  
	

If the editor crashes, **make sure it is the latest version of Lazy Shell by clicking the "(i)" button in the main window** and comparing the version there to the version posted on the home page 

If you are using the latest version, make a new post in one of these threads:
http://acmlm.kafuka.org/board/thread.php?id=7005
http://www.smwcentral.net/?p=viewthread&t=45572

Explain exactly what you did to produce this error or cause this disfunctionality to occur, what editor it was in, what order you did your actions to produce this error or disfunctionality, etc. Also, when the editor bugs out, an exception prompt appears. If you can manage to copy the error message after this:
************** Exception Text ************** and include it in your post, it will definitely help. But most importantly, you must explain in your post what you did. Only posting the exception text alone will not be adequate enough. The suggestions above are only suggestions. Sometimes only five words might be enough for me to quickly locate the bug and fix it. 

Remember, an error or bug is most likely NOT YOUR FAULT. Don't be afraid to report an error should it occur. I do notice and try to fix every bug that is reported, so your post won't be in vain (unless you're making a request for an addition to the editor, which I am now ignoring due to how time-consuming it can be).





