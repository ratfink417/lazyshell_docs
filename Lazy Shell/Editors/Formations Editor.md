This editor has 2 subwindows: NewFormations and packs.
# New Formations
A formation is a set of monsters encountered in battle. A formation is chosen when a battle is called through either an event script or through the property of an NPC in a level. Formation Index] Select the formation to load.

### Event
The battle event sequence that plays at the start of the battle. These can be edited in the animations editor.
### ??????
Unknown formation property; it is recommended to leave it alone. Only the Bowser, Kinlink formation has this value set by default.
### Type
The music assigned to the formation that plays in battle. The music can be selected from 8 indexes or set to {CURRENT}, which continues to play the current music track in the overworld when the battle begins. To edit the actual track that is assigned to the index, change the "Track" property below.
### Track
The music track assigned to the currently selected "Type" to the left. Note that changing this value will affect the music for all formations that use the same "Type" as the currently selected formation.
### Can't Run
If checked, it is impossible to run away from the formation in battle.
### Monster Number
A monster in the formation, by number.
### Monster Name
A monster in the formation, by name.
### X
The X coord, in pixels, of a monster in the formation.
### Y
The Y coord, in pixels, of a monster in the formation.
### Use
The monsters enabled in the formation. This must be checked for a monster that is to have any presence in the battle at all. It is not recommended to have more than 6 monsters enabled in one formation, due to VRAM capacity.
### Hide
The monsters not present in the formation at the start of the battle. Monsters with this property checked can be later called to battle through the battle-script.
### Formation Image
Click and drag the monsters in the formation. The actual boundaries of the image are beyond the visible boundaries as seen here and in-game, thus a monster coordinate of 0,0 or 255,255 may hide it completely.
### BG
Select the battlefield background to preview the formation in. This is only for preview purposes; changing this will have no effect on the ROM.

# PACKS
A pack is a set of three formations to either randomly or selectively choose from when a battle is called, through an event script or through an the property of an NPC in a level.

### Pack Index
Set the formation pack to edit by number.
### Formation 1
The 1st formation in the pack.
### Formation 2
The 2nd formation in the pack.
### Formation 3
The 3rd formation in the pack.
### Load
Load the 1st formation into the formation editor.
### Load
Load the 2nd formation into the formation editor.
### Load
Load the 3rd formation into the formation editor.
### Pack 1 Formation Collection
The list of monsters in the 1st formation.
### Pack 2 Formation Collection
The list of monsters in the 2nd formation.
### Pack 3 Formation Collection
The list of monsters in the 3rd formation.