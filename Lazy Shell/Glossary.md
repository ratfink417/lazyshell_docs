# GLOSSARY
## 2bpp & 4bpp
These mean "2 bits per pixel" and "4 bits per pixel", and refer to the format that graphics are in. Graphics in 2bpp format can only use a maximum of 4 colors, whereas 4bpp graphics can use up to 16 colors. 
The Big Boo in Bowser's Terrorize spell only needs 4 colors, thus the graphics are in 2bpp format to conserve ROM space.

## action queue
A group of commands in an event script which behave like a custom embedded action script, containing movement commands for a given NPC.

## action script
A script comprised of commands which create a series of movements ascribed to an NPC in a level. A townsperson walking back and forth randomly is controlled by an action script. A wiggler's unique behavior is governed by a special action script.

## AMEM
1. Audio memory, used to store SPC and sample data.
2. Animation memory, used in animation scripts to store sub-routine flags.

## animation script
The scripts which animate everything seen in battle. Attacks, spells, events, etc. are all governed by animation scripts. 

Animation scripts are, like battle and event scripts, written in their own scripting language. 

The animation scripting language is the most complicated and difficult to write for, as they tend to jump around wildly throughout the current bank by means of animation packets and memory-checking mini-scripts. 

The animations editor contains many powerful features, but unfortunately also many limitations on innovation. 

Some scripts are painfully large because many of the mini-scripts within a script are repeated numerous times.

## ASM
This is essentially the game's raw code which runs when the game is started. 

SNES games are generally written in assembly. 

Most everything that Lazy Shell modifies is arranged in data chunks and dynamic scripts and does not involve assembly programming code. 

Anything Lazy Shell is incapable of modifying, outside of the defense timing values. "ASM hacking" is modifying the assembly code outside of Lazy Shell.

## bit
These behave like flags or switches that are turned on or off. 

The game knows what has been done so far in the game because of the bits that are set or clear.
- Defeating the Hammer Bros. sets a bit. 
	Each time you enter that level, an event script checks if the switch is turned on in order to determine whether or not to show the Hammer Bros NPC and execute the associated cut scene. 
 
The "Jump" bit is already switched on when you start a new game, and can be switched off in the allies editor. 

Checkboxes in the editor are usually associated with bit-wise data while number values are byte-wise. 
- **Example:** monster HP is read byte-wise while elemental weaknesses are read bit-wise.

## command
These are what comprise the many scripts in the ROM. 
- **Example:** in the first encounter with Terrapins, an event script contains a command 
	`"Engage battle, pack: 1, battlefield: [07]"` 
	which initiates the battle with the Terrapins.
 
## element
The different things in the ROM that Lazy Shell can modify. 

The individual editors can usually edit one or two types of elements. Elements often have multiple indexes. 
Monsters are an element that has 256 indexes (0 to 255). 
Levels are another element that contains 510 indexes, event scripts have 4096 indexes.

## event script
The game basically progresses by event scripts. 

Everything you see happening in a level that isn't controlled by the player (ie. Mario) is executed by the commands in an event script. 

Scripts are usually initialized by a trigger in the level, when Mario comes into contact with either an event field or an NPC. 

An event script is also automatically initialized every time when entering a new level. This
script is the level's own event script (set with the "EVENT #") that usually contains commands for preparing primarily NPC and memory related elements before the level is completely loaded.

## event field
A field which, when Mario touches it, will initiate an event script.

Event fields can actually be made to behave exactly like exit fields and they often are when other commands must be executed. In these cases the scripts contain a command pointing to the target level.

## exit field
A field which, when Mario touches it, will load a new level.  Other ROM editors sometimes call these "entrances".

## field
An invisible thing in a level that triggers an event or operation when Mario touches it. Event and exit fields, for example.

## hex
A numeric system who's places are based on 16's and not 10's like in "decimal". 

With just one decimal place, you can count up to 9, but in just one hexadecimal place you can go up to 15. This is because the numbers 10-15 are A-F respectively. Thus in just two hexadecimal places the numbers can go up to 255, which is why this number is so common throughout the editor. 

With three hex places, 4096 is highest. The editor displays only memory addresses in hex format (eg. 00:709F) with all other elements being in decimal.

## index
**Examples:** 
	TERRAPIN is an index in the monster element (index 0). 
	The level for Mario's Pad is index 16 in the levels element, etc. 

You can modify the properties of each index by switching to or among them in the editors using either its drop down list or immediately with its numeric up/down.

## isometric
The pseudo 3-D orientation of Super Mario RPG. 

Other games like Final Fantasy Tactics and Tactics Ogre are isometrically oriented. Something is called "isometric" when, instead of being in a flat gridplane, it is shaped like a diamond and arranged at an angle. 

Nevertheless Mario RPG's levels are drawn with square 16x16 tiles and not diamond-shaped tiles, whereas the solidity tiles are.

## layer
SMRPG uses five layers: L1, L2, L3, NPCs, BG. By default, 

NPCs appear on top of all other layers (excluding priority 1 tiles).  After that, L1 appears on top, followed by L2, L3, and BG. 

The BG is simply the solid background color behind everything else.

## level
The places and areas you can enter in-game. Many ROM editors also refer to these as "locations".

## memory address
A "slot" where the game stores information that it needs to access later. 

**Example:** the 30 slots for items (7F:F882 to 7F:F89F) have memory addresses. The memory addresses are the items. 

Completed events, like defeating the Hammer Bros (00:7052, bit 6), are stored as a bit in a memory address. A memory address has 8 bits.

## mode 7
Mode 7 is a format in SNES which can display a 2D map in a 3D manner.

The 1st and 2nd mine cart levels are in mode 7 format, for instance. It can also do transformations such as the stretching effect on the world maps.

## mods
These can change the tiles or solidity tiles of a level. 

In the levels editor, there are two types of mods: tile mods and solidity mods.
**Examples:** 
- Croco blowing up the wall in Moleville Mines.
- The green button in Rose Town removing/adding stairs outside.

## mold
An arrangement of tiles that form a complete image (ie. a sprite image). 

A mold is similar to the orientation of a tilemap, except that sprite molds can either be in a format that arranges the tiles in a grid (gridplane) or a coordinate system (tilemap). 

One or more molds may be contained in a sprite or effect and are used to create a sequence animation.

## NPC
Abbreviation for "non-playable character". 

They are basically the sprites seen in-game in a level, excluding battles, but with a number of properties all described by the help tags in the levels editor. 

An NPC is not the same as a sprite, it merely has a sprite index assigned to it among a bunch of other attributes.

## OMEM
Object memory, referring to the object packets used in animation scripts. 

Each time a $68 or $64 command is called a memory address block is accessible exclusively by the current object, assigned by the parameters $68 or $64 commands.

## palette
A set of colors used to draw something. 

Almost all palettes are 16 colors, except for layer 3 graphics, fonts, and some effect graphics.

SNES games like SMRPG are somewhat limited in the number of colors they can display, which is why imported image files can decrease dramatically in quality. 

Many paint programs have features which can decrease the color depth of an image to 16 colors.

## priority
A tile or sprite's priority determines how it will overlap other tiles or how other tiles will overlap it. 

- **"Priority 1"** means someting will overlap all other parts of a level that aren't also set to priority 1.
- **Higher priority numbers** mean it will appear under other things.

Highlighting priority 1 tiles in a level will show what parts of the level will typically overlap Mario and NPCs.

## script
A list of 0 or more commands that carry out an action on screen in the game 

An exmaple might be Toad running into Mario near the beginning of the game, or Bowser's "Crusher" battle animation, or The Big Boo randomly selecting either "Lighting Orb" or "Bolt" to use in battle. 

**Examples:** event scripts, action scripts, battle scripts, animations.

## sequence
An animation. 

Two types of elements use sequences: sprites and effects.

A sequence is a collection of frames. Each frame is assigned a mold index from the sprite or effect's mold collection and plays back the frames as a fully animated sequence.

## solidity
The physical properties of something, like a map. Also varyingly called called "physical field" or "collision tiles". 

Levels in most games have solidity maps, but usually as tilesets associated with the regular graphical tileset. 

As tilesets in SMRPG are grid-based and not isometric like the solidity tiles, the tilemaps and not the tilesets have their own solidity maps.

## tilemap
An example: Levels are 64 rows of tiles, each row is 64 tiles. Many sprites are "tilemaps" themselves, but here each tile would have its own coordinate instead of being placed in a grid like levels. 

Do not mistake tilemaps with tilesets. "tileset" A collection or "palette" of tiles used to draw to a tilemap.

## trigger
When Mario comes into contact with something like an NPC or event field, and an event script is initiated, it is **"triggered"**. 

NPCs have a trigger property which sets the conditions for the script's initiation when Mario collides with it.