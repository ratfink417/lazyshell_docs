The game basically progresses by event scripts, outside of battle. Everything you see happening in a level that isn't controlled by the player (ie. Mario) is executed by the commands in an event script. Scripts are usually initialized by a trigger in the level, when Mario comes into contact with either an event field or an NPC. An event script is also automatically initialized every time when entering a new
level.

An event script is comprised of 0 or more commands, of which fall into two categories: event or action queue commands. Event commands generally alter or read things like memory, tell the script to jump to an address in the event data, etc. All of the options appear in each event command category in the category list on the top-right. Action queue commands only appear in an action queue for a specific NPC or object, such as Mario or the screen. These commands are usually coord-shifting and sequence playback commands for NPCs and other objects.
   
### Script Type
Select the type of script to load.
### Script Index
Select the event or action script to edit by number.
### Goto Address
Jump to the command at or closest to the given address.
### Script Commands
The list of commands (aka "command tree") in the current event script. 

Check the commands to delete, cut, or copy (using the toolstrip below), or double-click the commands to edit them in the box on the lower-right.
### Insert Command
Insert a new command after the selected command in the command list to the left.
### Apply Changes
Apply all changes made to the edited command.
### Action
Check this if you want to insert an action queue command into the currently selected command. Leave unchecked to insert an event command after the currently selected command.

# Select category
Select a category of event scripts, then choose from the commands in that category to create a new one. Some categories may need further explanation for the novice user.

### Objects
ie. action queues, will provide a list of objects to choose from for creating an action queue. These are mostly NPC #'s corresponding to the numbers in the NPC collection seen in the levels editor, but include other commonly used objects such as Mario or the screen layers.
### Jump to
commands will jump to an address within the current bank. So if the event script command offsets start with $1E, a jump to command with an address of $78FE will jump to $1E78FE. You cannot jump to an address outside of the bank, but you can jump to any one of the 4096 events using the commands in the "Events" category.
### Memory and Memory $7000
commands change and read values/bits stored in memory addresses. "Memory" commands generally read or modify bits in memory addresses $7045 and over. "Memory $7000" commands generally have fewer limits in that they are commonly used to check anything not associated with event bits, and are read/written on a byte basis hinstead of the bit basis $7045+ addresses are used for.
### Return
simply ends the script or the entire hierarchy of scripts.
 
# Action Queue Categories
Select a category of action queue commands, then choose from the commands in that category to create a new one. Some categories may need further explanation for the novice user.

### Properties
commands can modify the object's sprite attributes (several are associated with the NPC attributes box in the levels editor).
### Sprite sequence
commands can play back a sprite sequence or set to a single mold corresponding to the molds and sequences in the sprites editor.
### Shift
commands move the object on either a pixel or isometric basis, either by a given unit or by single unit.
### Jump to
commands will jump to an address within the current bank. So if the event script command offsets start with $1E, a jump to command with an address of $78FE will jump to $1E78FE. You cannot jump to an address outside of the bank, and jump to command inside an action queue should not jump outside of the queue.
### Memory and Memory $700C
commands change and read values/bits stored in memory addresses. "Memory" commands generally read or modify bits in memory addresses $7045 and over. "Memory $700C" commands generally have fewer limits in that they are commonly used to check anything not associated with event bits, and are read/written on a byte basis instead of a bit basis like $7045+ addresses. "Return" simply ends the action queue or the entire script.
### Commands
Select a command from the list of commands contained in the currently selected category above.
### Bytes Left
The remaining bytes available in the current bank. If the number here is negative, none of the scripts in the bank will save. The three banks ($1E,$1F,$20) have different amounts of free space.
### Hex
The raw hex data of the currently select event command in the command tree.
   
# Action Scripts
Action scripts are the behaviors of NPCs and other objects in a level. The random movements of townspeople are infinitely looping action scripts. The behaviors of monsters in a level are all action scripts. Action scripts are basically the same as action queues found in event scripts, except they can only contain action commands and aren't "triggered" like event scripts are. They're set and usually assigned to NPCs in the levels editor, but an NPC's action script can be changed within an event script.
