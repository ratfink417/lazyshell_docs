# F.A.Q. (FREQUENTLY ASKED QUESTIONS)

Q: The editor will not run at all.
A: You need .NET Framework 2 or higher installed on your system.

Q: I have no idea what this stuff means!
A: First, look in the glossary at the end of this readme file. Also, enable the help feature in the editor. If this feature is enabled, you'll be able to see a description of the property and what it does by moving the mouse over it. Click the (?) icon at the top of most editors or press F1 to enable/disable the help feature.

Q: I want to design or write a new _____. Where do I start?
A: If you're new to this, study the editor. Play around with it for a while before delving into a new project. Tweak or mess around with things that already exist (ex: scripts, levels, monsters, sprites, etc.) to gain an understanding of how everything works or operates.Then, when you want to start something new or original, use the "template-based" approach which I have always used in my own hacks: try thinking of something in the game that most closely resembles what you want to do or create, find that element in the editors, study it and it's properties/details, and use that as a template for your custom-made whatever. Example: copy event script commands into your own script that are similar, modify levels that are closest in resemblance to what you want to create, use existing monsters that are most characteristic of your custom monsters. The OREFFEZEPS hack, for example, was made entirely through this method of template hacking: I tweaked existing spells/attacks to varying degrees to make new original ones. The Bob-omb Mafia's forest levels used touched-up tilemaps of dummied maps which already existed (as well as the sewers levels).

Q: How do I add a new ally, item, monster, etc.?
A: You cannot add new indexes to any element, but you can replace the properties of existing indexes. That is the basic rule of hacking SMRPG. Many elements, like sprites, have dummied or unused indexes which you may edit or modify to "add" new stuff. Lazy Shell should not be viewed as an expansion tool but as a modification tool.

Q: Can Super Mario RPG be expanded?
A: Not with Lazy Shell, but I do believe there was an expansion hack project that successfully expanded the ROM. Lunar Expand is incapable of expanding SMRPG due to SA-1 chip complications.

Q: I'm looking specifically for _____ matching a name/description.
A: Most of the editors have a search field to the right of the index list, tagged with a magnifying glass icon. Use that to search for a specific index with a general description, name, or whatever.

Q: The editor crashed and/or corrupted the ROM and I lost my work!
A: First, try clicking "Ignore Error" and saving as a separate ROM. Then, try exporting the indexes that didn't glitch out into .dat files and import those into a fresh, uncorrupted ROM. In the future, enable the back-up feature in the settings: click the grey cog icon in the main window to open the settings. There are two types of back-ups: you can back-up on load and/or save. Thus you can roll back to an earlier edit before the ROM got corrupted by the program.

Q: I loaded a hack and one of the editors crashed.
A: It's possible the hack was written using an earlier version of Lazy Shell, particularly v2.x. Earlier versions of the program had badly written code and incorrectly saved certain types of data like sprites. Therefore newer versions will likely encounter errors with hacks made with earlier versions, and/or crash.

Q: What do these "B#,b#" things mean?
A: These are unknown bits. "B0,b0" means "Byte 0, bit 0" and refers to bit 0 in the first byte of the index's property data chunk. If you're confident you have discovered exactly what these bits do, feel free to post it in one of the bug report thread:
   http://acmlm.kafuka.org/board/thread.php?id=7005
   http://www.smwcentral.net/?p=viewthread&t=45572

Q: Is there free space in the ROM where I can insert graphics?
A: Only the space that you see in the editor's own graphics editor can be modified. You can import external images into it, or use the more powerful import features. For example, in the sprites editor.

Q: I have no idea how scripts work.
A: There are three types of scripts, each with their own scripting language: event, battle, and animation scripts. See the glossary for a more detailed explanation of scripts and how each different type of script works.

Q: Why do the images I import decrease in quality?
A: The number of colors are reduced to 15 (or 3 in 2bpp cases). So if you're trying to import a Caravaggio painting, you won't have much luck keeping the quality. Palettes are 16 or 4 colors, with the first color being reserved for transparent pixels.

Q: What's a .dat file?
A: Exported elements into external files that can be imported into other indexes of the same element.

Q: My ROM hack's checksum is bad/failed!
A: Only fresh, unsaved, unmodified ROMs will have a good checksum (0x3bb4). The ROM's checksum always fails after a save. It's not a bug because the slightest change in the ROM data will create a bad checksum. However if you are loading a fresh, supposedly unaltered ROM and get a failed checksum, then there may be issues.

Q: The editor crashes, regardless of what ROM is loaded.
A: Try resetting the settings. Click the cog icon in the main window and click "Default..." to reset the settings.

Q: Sometimes it asks to save even if I haven't done anything.
A: In some editors, like the sprites editor, switching between indexes will reassemble the last loaded index's data thus changing the data in the process. This is not a bug, and none of the properties are actually changed; just sometimes the raw hex data is slightly rearranged from the original order.

Q: What are Lazy Shell's most powerful features?
A: 1. The "Import Image(s)" functions in the sprites and effects editors allow the user to replace existing sprites with entirely new sprite animations from external image files. These were quite difficult to write the code for, but very rewarding in that they ultimately added a lot more muscle to the editor.

   2. The palette editor's "Adjust RGB" and "Effects" features let the
   user apply all kinds of effects to the colors, from RGB swapping,
   grayscale, contrast/brightness, colorizing, and more. You can create
   your own palette swaps of sprites, levels, etc. 
   3. The "New Font Table" feature in the dialogues editor in the font
   editor panel lets you replace the SMRPG font with any font installed
   on your system. 
   4. You can flip entire battlefields by just selecting the whole
   battlefield, right-click, and click "mirror" or "invert". 5. A
   built-in hex editor lets the user edit the raw hex data of several
   elements in the game.

## ALLIES
Q: Is it possible to add new allies?
A: No, you can only modify the existing five allies.

Q: Can I move another ally to the front to appear in the overworld?
A: Not in Lazy Shell, but with ASM hacking it is possible.

Q: Is it possible to start with other characters besides Mario?
A: You would have to switch the Mario sprite with another character's.

Q: Can I raise the XP to 5 digits and the coins to 4?
A: Not in Lazy Shell.
## ANIMATIONS
Q: How do I add things to a weapon or spell script?
A: These are called commands in the animation script editor, and you cannot add new ones: only replace, move or edit existing ones.

Q: I want to add new commands.
A: You cannot do this, you can only replace, move or edit commands.

Q: How do I replace commands?
A: Select the command and at the bottom of the editor replace the first hex value with the opcode of the command you want to replace it with.

Q: Where's the list of command opcodes for animations?
A: Download the documents archive at:
   http://home.comcast.net/~giangurgolo/smrpg/smrpg_docs.zip
   The docs_ani-code.txt file contains all opcodes decoded thus far.

Q: How do I make custom items with custom animations?
A: The easiest things to customize in the animations editor are the sprites used, the sound effects, and dialogues. "Current object = sprite: whatever" "Current sprite: whatever" "Current action object = effect: whatever" "Playback sound: whatever" are among them. It's better to start simple before working with stuff like memory.

Q: I want to change a sprite in an animation to something else.
A: You'll want to modify the "Current object = sprite: whatever" commands. Modify its properties in the "CURRENT COMMAND PROPERTIES" panel on the right and click apply when you are finished. Alternatively you can change the hex values below.

Q: How do I make allies use enemy spells/attacks?
A: This would require comprehensive animation script editing, including but not limited to careful repositioning of many effect and sprite graphics and changing behavior of the sprites, as well as changing the object memory addresses, etc. Example: "Light Beam" is specifically scripted to shift leftwards towards the allies, so to make it realistically target the monsters the initial position and direction would need to be changed among other things.

Q: Where are the locations of the dummy spell animation scripts?
A: There are none; dummy spells (except for the 4 nameless ones used by Smithy) have no pointers and no scripts.

Q: How do you modify damage in an animation script?
A: I cannot say for sure, but none of the animation scripts appear to contain commands that modify damage, aside from the CC command found only in ally spells that append damage.

Q: How do I replace Mushroom and Scarecrow with new effects?
A: Most likely it requires ASM hacking, but as this is an unexplored territory in the SMRPG ROM I cannot be sure.

## ATTACKS
Q: Can I make new "inflict functions" for a custom spell?
A: This involves ASM, thus you cannot do this in Lazy Shell.

## AUDIO
Q: Is there any way to add music to a SMRPG Rom?
A: Not in Lazy Shell; you can only modify the audio samples used by the music SPCs and the SPC instruments and tracks, not add new ones.

Q: Can I add sound effects?
A: Sound effects are also SPCs that use audio samples. Therefore the answer is no, like the above question. Some sound effects are empty which could be used to "add" custom sounds.

Q: I changed the instrument but it's muted in-game!
A: If the instrument is included among the percussives, you'll have to change the instrument index for the percussive as well.

Q: I modified some sound effects, but I can't hear any changes.
A: If you're loading from a save state outside of Lazy Shell, then the audio memory contained in the save state won't have the changes you made. This is because during sound effect playback the data is read from the memory instead of directly from the ROM, and all sound effect data is stored to memory when the ROM starts. The previewer, though, will let you hear the changes since the modified data is stored into the preview save state's audio memory.

Q: I imported an MML script but the channels are out of sync.
A: Sometimes you must delete the first rests contained in the last 7 channels.

Q: How do I transfer my work in the score writer to the SPC?
A: Export the staffs as scripts, then import the scripts into each of the individual channels. You'll have to manually add non-note commands in the track editor, like beat durations, volumes, etc.
## DIALOGUES
Q: I need some extra letters that my native language uses.
A: Use the empty slots in the font table. Letters that have accents or other diacritic marks can be drawn onto the new letters or imported as a new font table.

Q: How do I edit the names in the Level-up bonus screen?
A: This is found by selecting "Battle messages" in the battle dialogues editor.
## EVENT SCRIPTS
Q: I want to change an NPC's sprite's mold or sequence.
A: This must be done in an action queue. First insert an action queue with "Objects" > "Action queue...". Select the NPC from the menu. Then add the command "Sprite sequence" > "Seq playback, sprite +=".

Q: Can I make an NPC change colors/palettes?
A: This must be done in an action queue, using one of three types of commands. In the "Palette" category, choose one of the commands to shift the NPC's sprite's palette index forward. View the palettes using the sprites editor.

Q: Is there a default event script that is always running?
A: Not by default, but you can point the level's event script to a separate synchronous event that contains the memory-checking commands you want to run.

Q: How do I make a custom ending?
A: You can't edit the default ending sequence with Lazy Shell, but you can write a custom event script to run instead as long as the Smithy battle sequence doesn't run.

Q: How do I change a character's animation during a dialogue?
A: Make sure the "Run dialogue: whatever" command has the dialogue property "asynchronous" unchecked so any following commands that would change a sprite's animation sequence or whatever will run while the dialogue is playing. Use the "Pause script, resume on next dlg page" commands to pause the script after the animation is complete.

Q: I told my script to jump to index $11C, #284.
A: "Jump to $whatever" commands do NOT jump to indexes, they jump to addresses as seen in the [] to the left of each command.

Q: How do I make _____ the only active party member?
A: Through an event script use the command "Add/remove party member" in the "Party members" category.

Q: When I press The X button the inventory menu does not appear.
A: It must be made accessible using one of the "Joypad enable" commands in the "Joypad" category.
## FORMATIONS
Q: Some of the monsters in my formation are glitchy or discolored.
A: Too many monsters or having several large monsters in the same formation will overload the game's video memory and start smothering the graphics of other monsters and sprites. Do not put more than 6 monsters in a formation.

Q: My monster inexplicably changes palettes in battle. A: See the previous question.
## ITEMS
Q: I made a DUMMY item a weapon, but it freezes when used.
A: That's because it doesn't have an animation script. Unfortunately you cannot create or edit scripts for the DUMMY items in the animations editor because the ROM provides no extra space for it.

Q: Can I make new "inflict functions" for a custom item?
A: This involves ASM, thus you cannot do this in Lazy Shell.

Q: In the shops, there are two "Buy only, no selling" options.
A: They both do exactly the same thing.
## LEVELS
Q: My custom level just appears black in-game, music playing.
A: Make sure the layer mask's boundaries are within those of your new custom level and that Mario appears within those boundaries.

Q: How do I add something like an NPC to a level?
A: The tabs on the left panel, ex: the "NPCs" tab, contain buttons at the top of the tab window that let you insert, delete, copy, etc. NPCs, events, exits, overlaps, or mods.

Q: I notice that the NPC # does not correspond to the sprite #.
A: The help labels for the editor explain this. Hit F1 in the editor or click the (?) icon at the top of the levels editor.

Q: The NPCs are not showing.
A: Make sure "Show NPC instance" is checked.

Q: Some tiles keep overlapping the NPCs.
A: Those tiles most likely have priority 1 enabled on one or more of their subtiles. To stop this, replace the solidity tile at that spot with a corresponding solidity tile with the "Priority 1 enabled for objects on tile" checked. Otherwise, it could be an overlap tile. To stop this, delete the overlap at that spot.

Q: When I stand on the edge of a block it overlaps Mario and NPCs.
A: Look for a solidity tile with "Priority 3 for object on edge" enabled in the solidity tile search and draw it there.

Q: How do I get an NPC to start a dialogue?
A: The dialogues for NPCs are initiated in the NPC's event script. Open the NPC's event script or assign a new script # and insert a "Run dlg: whatever" command.

Q: The NPC graphics are glitchy in-game.
A: You'll want to try changing the "Partition" property. You can look for the best partition index for the level by using the parition searcher (accessible with the "Partition" button). Keep in mind the game only has so much video memory to store the sprites to, so too many large NPCs may just be impossible to show.

Q: I have no idea how these partitioning properties work.
A: Unfortunately, this is a grey area in my knowledge, as I am not completely sure how the game organizes video memory for NPC sprites on loading a level. Clone sprites (ex: multiple townspeople in the town levels) should be first in the NPC collection, and a partition that has the clone VRAM properties should be set to store them (3 or 4 sprites per row). Additionally, cloned sprites can only be gridplane format sprites. 3 sprites per row is set for 32px width sprites, 4 per row is for 24px width. Large sprites that overflow and write over cloned sprites might be fixed by setting clone buffer A to "empty buffer" to provide extra space for the large sprite.

Q: What does "Could not insert the _____" mean?
A: You'll need to delete other exits, events, npcs, or overlaps to insert new ones.

Q: Walking off an edge causes Mario to fall and get stuck.
A: Most likely you forgot to draw in a solidity tile somewhere. The isometric orientation of the solidity map sometimes makes it tricky to fill in all tiles. Also, make sure to seal off the edges of the walkable area with impassable tiles (usually with solid tile #255).

Q: How can I prevent a monster from reappearing after battle?
A: Look in the "AFTER BATTLE..." panel.

Q: Mario's Pipehouse is completely black.
A: For some reason the game applies the proper palette through ASM only for this level. If you want to see the level to edit it, change the palette to {21} temporarily then back to {50} when finished.

Q: I want a script to play infinitely in the background.
A: The level's "EVENT #" script must jump to a synchronous event that loops indefinitely during gameplay.

Q: I want to add a warp trampoline or pipe to another level.
A: Copy/paste a warp trampoline NPC from another level and edit the script to point to the desired target level. For the pipes, copy/ paste the event field at the pipe's coords from another level and edit the script likewise. Keep in mind you will be changing the target level for the original trampoline/pipe you copied from the other level as well.

Q: I want to add a monster to the level that starts a battle.
A: Set the "NPC TYPE" to "Battle" and the "Pack #" to the desired pack index. Remember, this is a pack index; not a formation index. Packs are three formations each, where one of the three is randomly selected for battle.
## MAIN TITLE
Q: How do I make my own title screen?
A: The easiest way is to make an image outside of Lazy Shell with a paint program (with the same dimensions as the title) and import the external image file in the Main Title editor. Right-click the layer 3 title logo and import the image. Creating an entirely new title screen is a very limited operation as there's only enough space for any new graphics and/or palettes that are imported.
## MINI-GAMES
Q: How do I delete/add mushrooms to stages 1 and 2?
A: You can't, the mushroom count is fixed to 8 for both stages.

Q: Why aren't the rails arching in stage 4 like in-game?
A: This is probably an effect applied by some code in the assembly I am not familiar with. Thus the rails appear flat in the editor.
## MONSTERS
Q: On a game over, things keep happening in battle.
A: Most likely the monster who inflicted the fatal blow has several consecutive attacks that need to have conditionals added to its script. "If target alive: at least one opponent" should be added before the commands following the initial attack.

Q: Battle commands keep executing one after another without stopping.
A: You'll need to add a "Wait 1 turn, restart script" or a "Wait 1 turn" command. The first is used within an "If" statement.
## SPRITES
Q: How do I add custom sprites?
A: You can only edit existing ones. You can import sprite images through several methods: import image files into a graphic set, import image files into the molds, etc. I strongly recommend importing images into the molds as the easiest way to make your own custom sprites from external image files.

Q: I want to replace a sprite with a new one from image files.
A: Use the mold import feature: the black down arrow and white box [v] icon directly over the mold list tagged "Import Image(s)". You may import one or more images over the current molds or append to the current molds.

Q: I want to change a monster's sprite to a different one.
A: Monster sprites are found in sprite indexes 256-511. If you want to change a specific sprite to another existing sprite, you'll need to change the "Image" and "Animation" values to that other sprite's image and animation values.

Q: How do I add tiles to a sprite?
A: You can only do this for tilemap formatted molds, not gridplanes. Select the tiles in the mold's tileset you want to draw and use the pencil tool to draw them.

Q: How do I create new tiles to draw with?
A: Once again, you can only to this for tilemap molds. Click "Insert new tile" (paper icon) at the top of the panel on the far right and manually set the subtiles.

Q: Are there any unused animation sequences?
A: http://tcrf.net/Super_Mario_RPG:_Legend_of_the_Seven_Stars Scroll
   down to the "Unused _____" sections.

Q: I get glitchy sprites when I load a save state.
A: This is not a bug with the editor nor the emulator. It is simply a matter of unsychronized memory: the newly edited ROM data for sprites is not sychronized with the save-state memory thus the glitchy sprites. This can be remedied by re-entering the area, which refreshes the memory.

Q: I want to make _____ a different color, or Mario without a hat.
A: Edit the palette and edit the graphics with the respective editors.

Q: Battle portraits appear discolored in the editor.
A: It appears like that in the editor, but the assembly manually applies the correct palette to the battle portraits.

Q: I can't find some sprites, even in the search.
A: Some sprites are within other sprites, nestled among the mold indexes. The nok-nok shell, for example, is molds 2-4 within the lazy shell sprite.