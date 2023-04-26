The places and areas you can enter in-game. Many ROM editors also refer to these as "locations" or "rooms". 

A single level is often a smaller part of a larger map, and is defined by a set of boundaries known as a "mask". Hence the appearance of multiple levels in the level image when a single level is selected.

These are all explained in the individual tab descriptions below.
   
# Level Index

![[Pasted image 20230425073951.png]]

Select the level to edit by name. The name is based on a label assigned by either the default or user-defined label. Edit the level's name/label by clicking on the label button to the right.

|Property      | Description|
|--------------|-------------|
|Level Index| Select level to edit by number|
|Level Name| The level's name/label. This is a property exclusive to the editor: changing this will not affect the ROM.|
|Event # Button|Opens the event scripts editor and loads the [[Event Scripts Editor\|event]] number|
|Event|The event # that initially runs when the level is first opened. If a custom level appears black or empty when opened, it's possible the event # does not contain a "fade in from black" [[Event Scripts Editor#Script Commands \| commands]].|
|Music|The music, or SPC track, that plays when the level is opened. This can be overridden by an event command.|


# Maps
The "MAPS" tab contains all the properties of a level's map.
![[Pasted image 20230425115252.png]]
The map is the collection of properties that set the tilemaps, palette, and tilesets for the level. 

Each level is assigned a "Map #" with all of the properties in the "MAPS" tab.

A graphic set is a loosely organized collection of 4bpp or 2bpp 8x8 tiles that are read from and organized into 16x16 tiles by a tileset. They are essentially the raw graphics used by a level.
   
A tileset is a set of 16x16 tiles (drawn using the graphic sets) which comprise what is essentially the set of tiles of which the final level image is drawn. **Note that tilesets do not contain any raw graphics, and are merely each a series of indexes in which 8x8 tiles are chosen from the graphic sets in the map**

A tilemap is a map of 16x16 tiles (drawn using the tilesets) which comprise what is essentially the final level image (for that layer only).

Many levels use the same map as other levels, such as the Booster Tower levels, because the area which generally constitutes the viewable boundaries of the level in-game is merely a portion of the entire map, where the boundaries are often set by the Layer Mask edges. 

If the boundaries are not set, then often when Mario walks to the far edge of a level, another part of the level's map which constitutes a different level can be seen.

| Property      | Description                                                                                                                                                                                                                                                                                                   |
|:------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Map #         | Set the level's map #                                                                                                                                                                                                                                                                                         |
| GFX Set 1     | The 1st graphic set in the current map.                                                                                                                                                                                                                                                                       |
| GFX Set 2     | The 2nd graphic set in the current map.                                                                                                                                                                                                                                                                       |
| GFX Set 3     | The 3rd graphic set in the current map.                                                                                                                                                                                                                                                                       |
| GFX Set 4     | The 4th graphic set in the current map.                                                                                                                                                                                                                                                                       |
| GFX Set 5     | The 5th graphic set in the current map.                                                                                                                                                                                                                                                                       |
| L3 GFX Set    | The graphic set used by Layer 3 in the current map. This is in 2bpp format.                                                                                                                                                                                                                                   |
| L1 Tileset    | The tileset used by Layer 1 in the current map.                                                                                                                                                                                                                                                               |
| L2 Tileset    | The tileset used by Layer 2 in the current map.                                                                                                                                                                                                                                                               |
| L3 Tileset    | The tileset used by Layer 3 in the current map.                                                                                                                                                                                                                                                               |
| L3 Priority 1 | If enabled, the 8x8 tiles in the tilemap's Layer 3 tiles that have the "L3 Priority 1" property enabled in the Layer 3 tileset will appear on top of all other tiles of all other layers.                                                                                                                     |
| L1 Tilemap    | The tilemap used by Layer 1 in the current map. Layer 1 is most often the "top" layer which usually includes things such as crates, trees, bushes, pipes, etc..                                                                                                                                               |
| L2 Tilemap    | The tilemap used by Layer 2 in the current map. Layer 2 is most often the "ground" layer which usually includes the entire floors, grounds, walls, etc. of a level image.                                                                                                                                     |
| L3 Tilemap    | The tilemap used by Layer 3 in the current map. Layer 3 is most often the "effect" layer which usually includes water, fog effects, translucent images, clouds, etc..                                                                                                                                         |
| Solidity Map  | The solidity map, also referred to as a physical map or collision tiles, is a map of solid tiles in the orientation of an isometric map. An isometric map is a 2D map that projects a 3D-like image. The solidity map can be shown/hidden using the block-like button in the toolstrip above the level image. |
| Battlefield   | The battlefield is the background image used by any battles that are encountered in the level. A level is assigned a battlefield "set" or a group of battlefields from which one is manually selected through an event script.                                                                                |
| Palette Set   | The palette set is a set of 7 palettes that comprise all of the colors that the level image uses.                                                                                                                                                                                                             |



# Layer
The "LAYER" tab contains all the properties of and effects applied to the level's layers.
![[Pasted image 20230425145539.png]]
### Message
The dialogue message that appears at the top of the screen when the
level is entered. These can be individually edited in the dialogues
editor. In order for a message to show, either the "SHOW MESSAGE" must
be enabled for any exit field that leads to the current level or an
event script command must be set for the current level's "Event #" in
the toolstrip bar at the top of this editor.

## Layer Priorities Section
![[Pasted image 20230425150206.png]]
### Priority Set
A set of properties that handles how the layers of the level are drawn. Note that editing the properties in the "Layer Priority" box for the currently set Priority Set will affect all other levels that use the same Priority Set.

#### Mainscreen
refers to the layers that are drawn opaquely (ie. normally without 'see-through' effects).
#### Subscreen
refers to the layers that are drawn translucently (ie. 'see through' effects). 

**Example:** many levels with water (which is translucent) have the water on L3 (which is commonly used for water, clouds, fog, etc.) which is enabled in the subscreen.Generally, at least one (usually all) layer is enabled in the "Color Math" that is also enabled in "Mainscreen" in order for the "Subscreen" layers that are enabled to appear at all. 
#### Color Math 
refers to the layers that the subscreen will appear over. If nothing is enabled in "Color Math" then the subscreen will not show at all. This is called "Color Math" because the colors of the subscreen are being added to or subtracted from the colors on the mainscreen, which creates a translucent effect for the subscreen.

### Intensity
"Half" intensity will halve the color values being added to or subtracted from. Example: if the mainscreen color has 128 for red and the subscreen color has 64 for red, then the final color will be (128/2) + (64/2) or 64 + 32 (or subtracts depending on the "Mode").This generally creates a darker effect of the subscreen. "Full intensity will add or subtract the full values of the colors. 

**Example:** if the mainscreen color has 128 for red and the subscreen color has 64 for red, then it adds 128 + 64 (or subtracts depending on the "Mode").This creates a much brighter effect than "Half" intensity.

### Mode
"Plus" mode will add the colors of the subscreen together. "Minus" mode will subtract the subscreen colors from the mainscreen colors. This creates a much darker effect. In reference to the other "Layer Priority" properties, anything referring to an either/or case of subtracting or adding is referring to the "Mode" property.

| Form Element   | Description                                                       |     | 
| -------------- | ----------------------------------------------------------------- | --- |
| L1 Mainscreen  | Layer 1 of the mainscreen.                                        |     |
| L2 Mainscreen  | Layer 2 of the mainscreen.                                        |     |
| L3 Mainscreen  | Layer 3 of the mainscreen.                                        |     |
| NPC Mainscreen | NPC layer of the mainscreen.                                      |     |
| L1 Subscreen   | Layer 1 of the subscreen.                                         |     |
| L2 Subscreen   | Layer 2 of the subscreen.                                         |     |
| L3 Subscreen   | Layer 3 of the subscreen.                                         |     |
| NPC Subscreen  | NPC layer of the subscreen.                                       |     |
| L1 Color Math  | Add / subtract subscreen from Layer 1 of the mainscreen.          |     |
| L2 Color Math  | Add / subtract subscreen from Layer 2 of the mainscreen.          |     |
| L3 Color Math  | Add / subtract subscreen from Layer 3 of the mainscreen.          |     |
| NPC Color Math | Add / subtract subscreen from NPC layer of the mainscreen.        |     |
| BG Color Math  | Add / subtract subscreen from background layer of the mainscreen. |     |

## Layer Mask Edges Section
![[Pasted image 20230425150427.png]]

### Lock Scrolling
If checked, the screen will be unable to scroll past the edge of the layer mask. The layer mask sets the viewable boundaries of the level. Anything beyond these boundaries will not appear in-game. Click the orange box in the toolstrip to show the layer mask.
| Form Element | Description | 
| ------------ | ----------- |
|Right|The right edge, in 16x16 tile units, of the layer mask.|
|Left|The left edge, in 16x16 tile units, of the layer mask.|
|Bottom|The bottom edge, in 16x16 tile units, of the layer mask.|
|Top|The top edge, in 16x16 tile units, of the layer mask.|

## Layer -(X,Y) Shifting Section

### L2 -X shift
Amount L2 is shifted left, in 16x16 tile units.
### L2 -Y shift
Amount L2 is shifted up, in 16x16 tile units.
### L3 -X shift
Amount L3 is shifted left, in 16x16 tile units.
### L3 -Y shift
Amount L3 is shifted up, in 16x16 tile units.
### Layer Scrolling Wrap
Scrolling layers will wrap around infinitely. For practical purposes, "horizontal" and "vertical" are generally checked together for a layer if either one is checked at all.

**NOTE: This is ignored if "Speed" in the "Layer Auto-scrolling" box for the layer is set to (none).**
### L2 Vertical Synchronization
The amount of layer 2's desynchronization when Mario walks up/down. This refers to the speed in which the screen scrolls up/down in the opposite direction when Mario walks up/down. This rarely used. Example: in Bowser's Castle in the throne room, where the Chandeliers (layer 2) have a "Low" horizontal and vertical desync value. This means the chandeliers will move left more slowly when Mario walks to the right, and move right slowly when Mario walks left. The same applies vertically.
### L2 Horizontal Synchronization
The amount of layer 2's desynchronization when Mario walks left/right. This refers to the speed in which the screen scrolls left/right in the opposite direction when Mario walks left/right. This rarely used. Example: in Bowser's Castle in the throne room, where the Chandeliers (layer 2) have a "Low" horizontal and vertical desync value. This means the chandeliers will move left more slowly when Mario walks to the right, and move right slowly when Mario walks left. The same applies vertically.
### L3 Vertical Synchronization
The amount of layer 3's desynchronization when Mario walks up/down. This refers to the speed in which the screen scrolls up/down in the opposite direction when Mario walks up/down.
### L3 Horizontal Synchronization
The amount of layer 3's desynchronization when Mario walks left/right. This refers to the speed in which the screen scrolls left/right in the opposite direction when Mario walks left/right.
### Infinite
For layers that have autoscrolling enabled (ie. the "Speed" for the layer is not set to (none)) the layer will scroll indefinitely. This property is ignored for layers that don't have "SCROLL WRAPPING" enabled.
### L2 Shift
This will initially shift layer 2 some pixels before starting the autoscroll. No point is seen to this property, so it is recommended to leave it alone.
### L3 Shift
This will initially shift layer 3 some pixels before starting the autoscroll. No point is seen to this property, so it is recommended to leave it alone.
### L2 Direction
The direction layer 2 will scroll. This property is ignored if "L2 Speed" is set to (none).
### L2 Speed
The relative speed at which layer 2 will scroll.
### L3 Direction
The direction layer 3 will scroll. This property is ignored if "L3 Speed" is set to (none).
### L3 Speed
The relative speed at which layer 2 will scroll.
### Rippling Water
This, if enabled will create a "rippling water" effect on the subscreen layers.
### L3 Animation Effects
The various animation effects that can be applied to layer 3.
### Sprites Animation Effects
The various animation effects that are applied to sprites and other layers.
   
# NPCs
An "NPC" is a "non- playable character", or generally referred to as sprites although the use of the word "sprites" for this may be misleading since most NPCs do not correspond to the sprite index. 

Add, remove, duplicate, cut, copy, paste NPCs or NPC clones using the toolstrip above the NPC collection. 

You will notice in the NPC collection treeview some NPCs have child nodes, which here are referred to as "Clones" of an NPC. An NPC clone is an NPC that shares all of the same properties of its parent NPC (ie. the NPC it is an instance of) save for those fields not disabled when a clone is selected. Each clone has its own coords.

Only up to 3 NPCs may contain clones. Clones *must* come first in the collection and *must* use gridplane format sprites for the partition to store them to the video memory's clone buffer properly.

### NPC Collection
The collection of NPCs in the level.
### Partition
Set the level's partition packet.
### Partition Browser
Find a partition with specific properties.
### Type
Some properties of the NPC change based on it's type.

#### Object
is generally used for normal NPC's such as the characters in a town that trigger dialogue.
#### Treasure
is typically used for treasure chests.
#### Battle
is typically used for monsters that trigger a battle.

### Trigger
This refers to how the event (assigned by the "Event #") will be triggered.
### NPC #
The NPC assigned to the currently selected NPC.
### NPC Browser
Since NPCs don't correspond to the actual Sprite # as seen in the Sprites editor, this browser/editor is required to find NPC's that use a specific sprite #.
### BUTTON: Event # / Pack #
If "Type" is set to "Object" or "Treasure", this will open the event scripts editor and load the event #. If set to "Battle" it will open the formations editor and load the pack #.
### BUTTON: Action #
Opens the event scripts editor and loads the action #.
### Event / Pack #
If "Type" is set to "Object" or "Treasure", this will execute an event script when the NPC has been triggered.

If "Type" is set to "Battle", this assigns a pack to the NPC to be accessed when the NPC has been triggered.

Edit the event or pack by clicking the button to the left.
### Action #
The action # that is initially assigned to the NPC when the level is first entered. The action is the general movement and behavior of the sprite, e.g. walking back / forth randomly. Click the button to the left to edit the action #.
### Speed +
This will usually increase the speed of the NPC's playback.
### Show NPC
This must be enabled for the NPC to initially appear in the level.
### NPC #+ / $70A7 = / Action #+
If "Type" is set to "Object", this value is added to the NPC #. The purpose of this is to allow clones to use a different NPC # than their parent, but only within an index range of 7. 

Example: if "NPC #+" is 3 and "NPC #" is 15, then the clone will be assigned NPC # 18. 
If "Type" is set to "Treasure", this value is stored to memory address $70A7. $70A7 can be accessed in event scripts to determine what the item # or what type of item (ie. mushroom, super star, flower, etc.) will be given or shown for the treasure chest.
If "Type" is set to "Battle", this value is added to the "Action #". The purpose of this is to allow clones to use a different action # than their parent, but only within an index range of 15. Example: if "Action #+" is 3 and the "Action #" is 15, then the clone will be assigned Action # 18.
### Event / Pack #+
If "Type" is set to "Object", this value is added to the Event #. The purpose of this is to allow clones to use a different Event # than their parent, but only within an index range of 7. 

Example: if "Event #+" is 3 and the "Event #" is 15, then the clone will be assigned Event # 18. 
If "Type" is set to "Treasure", this value refers to "Treasure" or the type of treasure the NPC will give you if it is triggered. Here is the default list of treasure types: 
 0 = mushroom 
 1 = invincible star 
 2 = flower 
 3 = frog coin. 
 Other values might refer to an item # that the treasure rewards, but this is usually declared by an event script.
 
 If "Type" is set to "Battle", this value is added to the "Pack #". The purpose of this is to allow clones to use a different action # than their parent, but only within an index range of 15. 
 
 Example: if "Pack #+" is 3 and the "Pack #" is 15, then the clone will be assigned Pack # 18.
### Action #+
If "Type" is set to "Object", this value is added to the "Action #". The purpose of this is to allow clones to use a different action # than their parent, but only within an index range of 3. 

Example: if "Action #+" is 3 and the "Action #" is 15, then the clone will be assigned Action # 18.
### After Battle
The behavior of the NPC after battle, either having won or ran away.
### X
The isometric X coord of the NPC. For manual editing, use the "Isometric Coords" label below the level image.
### Y
The isometric Y coord of the NPC. For manual editing, use the "Isometric Coords" label below the level image.
### Z
The isometric Z coord, or the elevation, of the NPC.
### +1/2
If enabled, the Z coord is increased by half a unit.
### F
The F coord, ie. the direction the NPC faces.
### Other Properties

#### Face on trigger
will cause the NPC to face Mario when it has been triggered.
#### Sequence playback
must be enabled for any sprite sequences (ie. animations) of the NPC to play.
#### Can't float
will cause the NPC to fall to the ground if its Z coord is higher than the top of the floor.
#### Can't walk under
will not let Mario or any NPC's to walk under the NPC.
#### Can't pass walls
will not let the NPC pass through walls.
#### Can't jump through
will not let Mario or any NPC's beneath it to jump through the NPC.
#### Can't pass NPCs
will not let the NPC pass through NPCs
#### Can't walk through
will not let Mario or any NPC's to walk through the NPC.
#### Slidable along walls
prevents the NPC from "sticking" to a wall if moving alongside it.
  
# Exits
An "Exit" is an isometric field that, when walked into, will open the level or world map location defined in the "Destination Properties" box.

Add, remove, copy, paste, and duplicate exits using the toolstrip above the exit field collection.
   
### Exit Field Collection
The collection of exits, or entrances, in the level.
### Destination Properties
The level or location (depending on the value "Type" is set to) that will open when the exit is triggered.
### Show Message
This will display a 1-line dialogue at the top of the screen when the destination level is opened. Change the message for the destination level in the "LAYER" tab.
### Type
Determines whether the destination is a level or location.
### X
The isometric X coord of the Exit field. For manual editing, use the "Isometric Coords" label below the level image.
### Y
The isometric Y coord of the Exit field. For manual editing, use the "Isometric Coords" label below the level image.
### Z
The isometric Z coord, or the elevation, of the Exit field.
### Length
The length, in isometric units, of the field.
### Height
The height, in isometric units, of the field.
### F
The F coord, ie. the direction or orientation the Exit.
### NW/SE edge active
This will enable the trigger on the NW/SE edges of the field.
### NE/SW edge active
This will enable the trigger on the NE/SW edges of the field.
### X
Mario's initial isometric X coord in the destination level.
### Y
Mario's initial isometric Y coord in the destination level.
### Z
Mario's initial isometric Z coord, or elevation, in the destination level.
### F
Mario's initial F coord (F direction) in the destination level.
### +1/2
Increases Mario's initial isometric Z coord at the new destination by half.
   
# Events
An event field is an isometric field that, when walked into, will trigger an event #.
Add, remove, copy, paste, and duplicate event fields using the toolstrip above the event field collection.
   
### Event Field Collection
The collection of event fields in the level.
### BUTTON: Event #
Opens the event script editor and loads the event #.
### Event #
This is the event # that will run when the event field has been triggered.
### X
The isometric X coord of the event field. For manual editing, use the "Isometric Coords" label below the level image.
### Y
The isometric Y coord of the Event field. For manual editing, use the "Isometric Coords" label below the level image.
### Z
The isometric Z coord, or the elevation, of the Event field.
### Length
The length, in isometric units, of the event field.
### Height
The height, in isometric units, of the event field.
### F
The F coord, ie. the direction or orientation the event field.
### NW/SE edge active
This will enable the trigger on the NW/SE edges of the field.
### NE/SW edge active
This will enable the trigger on the NE/SW edges of the field.
   
# Overlaps
An "overlap" is an object that hides NPCs under all layers. Add, remove, copy, paste, and duplicate overlaps using the toolstrip above the overlap collection.
   
### Overlap Collection
The collection of overlaps in the level.
### Tile #
The tile # assigned to the overlap. Set the tile in the tileset below.
### X
The isometric X coord of the Overlap. For manual editing, use the "Isometric Coords" label below the level image.
### Y
The isometric Y coord of the Overlap. For manual editing, use the "Isometric Coords" label below the level image.
### Z
The isometric Z coord, or the elevation, of the overlap.
### +1/2
Increases the Z coord by half a unit.
### Other Properties
The remaining properties of the overlap.
   
# Tile Mods
Tile mods are modifications to a level tilemap's tiles, usually done through an event script. 

Common examples include manually opening and closing doors through event commands, which require a tile mod to change the tiles to an open/closed door. A tile mod can also have an "alternate" tile mod, which can be selected in preference to the parent tile mod through an event script command's properties.

### Tile Mod Collection
The collection of tile mods for the level.
### X
The X coord of the tile mod.
### Y
The Y coord of the tile mod.
### Length
The length, in isometric units, of the tile mod.
### Height
The height, in isometric units, of the tile mod.
### Layers
The layers included in the tile mod, to be edited in the level map. If no layers are selected, the tile mod will have no effect on the level.
   
# Solid Mods
A solid mod is similar to a tile mod in that the solidity map can be manually altered through an event script command. Its placement and dimensions, of course, are isometric.
   
### Solid Mod Collection
The collection of solid mods for the level.
### X Coord
The isometric X coord of the solid mod.
### Y Coord
The isometric Y coord of the solid mod.
### Length
The length, in isometric units, of the solid mod.
### Height
The height, in isometric units, of the solid mod.
   
# Space Analyzer
The Space Analyzer window is for monitoring the space available in the banks that store the compressed level map data for tile maps and solidity maps. 

The size of the uncompressed map data that the user interacts with in the editor is compressed to analyze the actual space which will be used in each bank.

Each tab contains the entire list of tilemaps and solidity maps used by all levels, and the data for accessing each. Collections of rows are color-coded to separate the banks from one another. 

The most important column is probably the "Bytes left" column, which shows how many available bytes there are for that bank, starting at that map. If one or more rows (ie. maps) at the end of the bank are red, then there is not enough space to store all of the compressed maps and the editor will fail to save those map rows marked red.
   
### Tile Maps
 This is the entire collection of tilemaps for all levels.
### Solidity Maps
 This is the entire collection of tilemaps for all levels.
   
# SOLID TILES
Here a solidity tile is selected to draw to the level map. Solidity tiles, like the solidity map they're drawn in, are isometric in make-up.  All of these properties are in isometric units.

Solidity tiles are color-coded. Places where there are no tiles at all can be walked on. Grey tiles are tiles that can also (generally) be walked on. 

Slanted grey tiles are stairs that can be walked on. 
Pink tiles are those tiles or portions of tiles that cannot be walked on at all. 
White tiles are "floating" tiles, or tiles that hover above a base tile of the same tile. 
Dark grey tiles are simply base tiles which have a "floating" tile above them. 
Light blue tiles are water tiles that can be waded through. 
Dark blue tiles are water tiles that can be swum through. 
Green tiles are vine tiles that can be climbed.

A solidity tile is arranged in four quadrants (north, south, east, west) each quadrant having its own set of properties. It also has four edges (NW, SW, NE, SE) which also have a set of attributes. The following is a list of the most common solidity tiles:
   
`Tile #0` is the empty tile: erasing a tile is the same as drawing tile #0 in its place. Therefore it is strongly recommended to leave this tile alone.
i`Tile #255` is commonly used to set the physical boundaries of a level, just as the layer mask sets the visible boundaries.
`Tile #256` is exactly the same as tile #0, only that it has priority 3 for objects that walk on it.

### Solid Tile Index
Select the solid tile to load.
### Height of base tile
The height of the solidity tile from ground zero.
### Height of overhead tile
An overhead tile is a solid tile that floats above the base tile. This is its height. If this is set to 0, there is no overhead tile.
### Z coord of overhead tile
The elevation of the overhead tile. This value must be greater than or equal to the base tile's height.
### Z coord of water tile
This is the surface of the water. If landed on, Mario will float on the surface. 

If walked under, Mario goes underwater. "Special tile format" must be set to "water", otherwise this will be ignored. This value must be higher than the height of the base tile. If this is set to 0, there is no water tile.
### Z coord plus 1/2
Raises the Z coord, or elevation, of the overhead tile by half an isometric unit.
### N
If "Solid quadrant flag" is enabled, the north quadrant of the tile is impassible.
### W
If "Solid quadrant flag" is enabled, the west quadrant of the tile is impassible.
### E
If "Solid quadrant flag" is enabled, the east quadrant of the tile is impassible.
### S
If "Solid quadrant flag" is enabled, the south quadrant of the tile is impassible.
### Solid tile
The entire tile becomes impassible, all other properties are overridden.
### Solid quadrant flag
This must be set for any of the solid quadrants above to be effective.
### NW
The north-western edge cannot be passed.
### NE
The north-eastern edge cannot be passed.
### SW
The south-western edge cannot be passed.
### SE
The south-eastern edge cannot be passed.
### P3 for object on edge
Mario or any NPCs on top of the tile's edges will overlap all other map layers.
### P3 for object over edge
Mario or any NPCs above the tile's edges will overlap all map layers.
### P3 for object on tile
Mario or any NPCs on the surface of the tile will overlap all map layers.
### Conveyor belt runs
The direction the conveyor belt runs, if the tile behaves as a conveyor belt (see next two properties).
### Conveyor belt, fast
Enable this to create a fast conveyor belt effect on the tile.
### Conveyor belt, normal
Enable this to create a conveyor belt effect on the tile. If neither this nor the fast one is set, the tile will not act as a conveyor belt.
### Stairs lead
The tile can act as a set of stairs, if not set to {none}.
### Special tile format
The tile can act as a vine that can be climbed or a water tile, or neither.
### Door format
Walking on this tile will do an automatic tile mod door effect on the map layers its placed at. 

Notice that the door tiles in the layer tileset must be in layer 1 and must be in the same position in the tileset image they are found in all levels with doors. Otherwise the solid tile's automatic tile mod function will set the tiles to whatever is at the default index of the door tiles.

Some of these properties are unknown, but seem to call automatic tile mods.
### Unknown Bits
These are all unknown bits.

# MAIN TITLE
The main title screen is the first thing you see, after the Squaresoft logo, when the game first initializes. 

It is a 3-layer image, composed of 3 tilesets with a separate palette applied to each. 

The 1st layer is the keep and cliffs, 
The 2nd layer is the blue background and clouds
The 3rd is the title art for the Super Mario RPG logo. 
	The 3rd layer is in 4bpp format and 256x56 pixels.
   
## Main Title Preview
The final product of all 3 layers as drawn in-game.