# PREVIEWER
Launch an emulator from the previewer window and load a save state for easy ROM testing. 

Choose either the SNES9X or ZSNES emulator file to use when opening the previewer. ZSNES will automatically load the generated save state when the emulator is loaded from the previewer, but for SNES9X the F1 key must be pressed manually to load the generated save state. 

If the emulator has problems loading the save state, make sure the 2 steps above have been completed.  The latest version of ZSNES (v1.51 as of this release) is supported. Snes9x v1.43 and/or its derivatives (rerecord, Geiger's debugger, etc.) are preferred and should work. Before using the previewer, do the following: 
   1. Make sure all editor files are in the same folder.
   
   2. Configure the emulator's save-state folder to read/write to the same folder as any loaded ROM. ZSNES by default already does this, and so does Snes9x v1.43. However, later versions of Snes9x will by default read/write to a "Save" folder created within the emulator's main folder, and if not changed it will fail to load the preview save state.
   
### Emulator Path
The path of the emulator executable file.
### Rom Path
The location the preview ROM used for previewing will be stored to.
### Dynamic
If enabled the preview ROM will write to the location of the ROM currently loaded to Lazy Shell. If not, it will write to the location of the Lazy Shell .exe file.
### SNES9X Args
Command line arguments for when the Snes9x emulator runs by command line. Snes9x cannot automatically load a save state by command line so it must be loaded manually with F1.
### ZSNES Args
Command line arguments for when the ZSNES emulator runs by command line. Here the default will automatically load the save state to jump to the preview.
### Source of Entrance
Choose from a list of sources to set the previewer's save state to. 

For levels this list is generated from the entrances of other levels leading to the desired level to preview. 

Event scripts will produce a list of levels and coordinates where there are event fields assigned that script. 

Animation scripts will open a battle and depending on the category will either load a formation with a monster who executes the attack / spell animation or set the item inventory to contain the item to preview, etc.

SPCs will have no list and simply load a black screen then playback the song or sound effect.

Mine cart levels will simply load the level at the same coordinates.

The level may take a bit longer to load than other previewable elements.
### Index
Either the index of the element to preview or a resource element to preview the currently selected index of whatever editor the previewer was opened from.
### X
Mario's initial X coord when a level loads in the emulator
### Y
Mario's initial Y coord when a level loads in the emulator
### Z
Mario's initial Z coord, or elevation, when a level loads in the emulator
### Battlefield
Set this for previewing elements which are battle-oriented like monsters or animations.
### Allies in Party
Active allies in the party for the preview.
### Ally
Select the ally to set their level and equipment for the preview.
### LV
Set the level of the ally for the preview.
### Weapon
Equip the ally with a weapon for the preview.
### Armor
Equip the ally with armor for the preview.
### Accessory
Equip the ally with an accessory for the preview.
### Max Stats
Checking this will max out the stats of all allies and give them with the best equipment.
### Reset
Reset the ally's level and equipment.
### Launch
Generate the preview ROM + save state and launch the emulator.

# PALETTES
Here a palette or palette set can be modified and a number of effects can be applied to it. 

The RGB can be typically modified in the "Color levels" box, while many common color transformations are available in the "Adjust RGB" and "Effects" tabs.

The "Switch" and "Equalize" boxes make it easy to create a custom palette swap of a sprite, level, etc. Under the "Effects" tab other

common color transformations are found, as well as a "Threshold" and "Colorize" feature.

The swatch box on the bottom-right is available for setting the selected color in the palette to any generic color in the swatch.
   
### Palette
The palette or palette set. It's arranged in one or more rows, each row being a single palette in the set. Checking any of the buttons above or to the left will apply the palette effects set in the "Adjust RGB" and "Effects" tabs below. The buttons above will apply effects by column, the buttons to the left by row.
### Current Color
The currently selected color. Its RGB levels can be changed in the box on the right.
### R
Red level of the selected color.
### G
Green level of the selected color.
### B
Blue level of the selected color.
### HTML
The RGB levels in HTML, or hexadecimal, format.
### Set To Color
Sets the selected color in the palette set to the color in the box on the right.
### Color Swatch
Pick a color in the swatch to load into the little box above, and usethe "Set to color" button to set it as the palette set's selected color.
### Update
Applies all changes made in the palette editor to the source's palette set.
### Auto-update
Automatically apply any changes made in the palette editor to the source's palette set. If unchecked, click "Update" to apply the changes.
   
## Adjust RGB
### Reds
Raise or lower the color level of the palette's reds.
### Switch reds
Switches the palette's reds with what's selected in the "With" box.
### Switch greens
Switches the palette's greens with what's selected in the "With" box.
### Switch blues
Switches the palette's blues with what's selected in the "With" box.
### With reds
Switches what's selected in the "Switch" box with the palette's reds.
### With greens
Switches what's selected in the "Switch" box with the palette's greens.
### With blues
Switches what's selected in the "Switch" box with the palette's blues.
### This (reds)
The palette's reds will be equal to what's selected in the "Equals" box.
### This (greens)
The palette's greens will be equal to what's selected in the "Equals" box.
### This (blues)
The palette's blues will be equal to what's selected in the "Equals" box.
### Equals reds
Whatever's selected in the "This" box will equal the palette's reds.
### Equals greens
Whatever's selected in the "This" box will equal the palette's greens.
### Equals blues
Whatever's selected in the "This" box will equal the palette's blues.
   
## Effects
### Greyscale
The palette set will be converted to greyscale.
### Negative image
The palette set's colors will be inverted.
### Brightness
Relative brightness of the palette set. 0 is default, move left or right to darken or brighten the palette.
### Contrast
Relative contrast of the palette set. 0 is default, move left or right to lower or raise the contrast.
### Threshold
Apply a threshold effect on the palette set.

A threshold effect will reduce the palette to two colors: black and white. The level of the threshold is the ratio of white to black: the higher the threshold, the darker colors will be converted to 0, or solid black. Lower thresholds will convert more colors to white.
### Threshold
The threshold level to apply.
### Colorize
Apply a colorizing effect on the palette set.
### Hue
The hue, or color, to colorize the palette set with.
### Saturation
The level of saturation the colorization effect on the palette set. Lower values will make the colors greyer, higher values more colorful.
# GRAPHICS
Paint edit a set of 4bpp or 2bpp graphics used by an element in the ROM. 

The user can edit the graphics directly or save the graphics as an image to edit in an external paint program (this is preferred for more in-depth editing). The graphics image can be re-imported after the external editing has been done.

Here a color in the palette set can be selected to draw to the graphics image. Both a front and back color can be selected to be drawn using the left or right click buttons.
   
## Palette Set
Choose a color to draw with in the graphics below. 

Right-click a color to draw with using the right mouse button. The graphics image below can only use a single palette row (16 colors) therefore clicking a color will show the graphics image using that color's palette row. 

Changing the palette row this way will NOT modify the ROM data, only how the graphics image is shown. 

Different objects in the image will use different palettes, so select the proper row to view a set of objects with their appropriate palette.
### Front Color
Draw this color to the graphic set using the left mouse button.
### Back Color
Draw this color to the graphic set using the right mouse button.
### Contiguous
Fill a region with the front color. If unchecked, all pixels with the  filled color in the entire graphics will be filled with the new color.
## Graphics
Draw, erase, fill, pixels, select/replace a color, or zoom in/out using the toolstrip above. 

Only single pixels can be erased or drawn. Import an image with the right-click context menu.
**NOTE: when importing an image, the top-right corner of the new image will be pasted to the place where you right-clicked.**
### Update
Applies all changes made in the graphics editor to the source's graphics.

### Auto-update
Automatically apply any changes made in the graphics editor to the source's graphics. If unchecked, click "Update" to apply the changes.
# TILE EDITOR
Edit a 16x16 tile's subtiles. 

A subtile is 8 pixels wide and 8 pixels high and has several distinct properties. Usually more practical transformations to the tileset can be done more easily outside of the tile editor with a right-click context menu.
   
### Tile
The 16x16 tile loaded. Click the quadrants to load a subtile.
### Subtile
The 8x8 subtile loaded. Edit its properties in the "Subtile properties"  box below.
### Index
This value corresponds to the 8x8 tiles in the graphics editor. A tile's index is shown in the label below the graphics image.
### Palette
The palette row, or index, used by the tile from its source's palette set.
### Properties
"Priority 1" will give the subtile priority 1 status. "Mirror" will flip the subtile horizontally, "Invert" flips it vertically.
### Mirror
Flips the 16x16 tile horizontally. Note that doing this will change the "Mirror" properties of all 4 of its subtiles.
### Invert
Flips the 16x16 tile vertically. Note that doing this will change the "Invert" properties of all 4 of its subtiles.
### Update
Applies all changes made in the graphics editor to the source's graphics.
### Auto-update
Automatically apply any changes made in the graphics editor to the source's graphics. If unchecked, click "Update" to apply the changes.
## TILESETS
For levels, these are the level's tilesets for each of the 3 layers. 

If layer 3 is not enabled for the level the layer 3 tab is inaccessible. 

Tilesets for the main title can be modified exactly in the same nature as level tilesets, with a couple of differences. The first being the format of layer 3, and the second being the ability to import an external image file as a single layer in just a few steps. This feature is accessible by right-clicking the tileset image. Mine cart levels, both mode 7 and side-scrolling, have only one tileset to draw from.
   
## Layers
Select the layer and tileset to edit or draw from. 

To erase, draw to, etc. a specific layer in a level's (tile)map/image select the layer among the tabs available. Note that selecting a tab in the level editor will set the layer being edited for both the tilemap and the tileset.

You can only draw layer 1, 2, and 3 tiles to their respective layers. Cross-layer drawing is not possible. However, layer tilesets will most often have identical tiles to draw the same tiles to different layers.

You will notice that there are often repeats of tile groupings in a tileset, ie. two identical crates, grass patches, etc. This is because one grouping has priority 1 set, the other does not. Mario and NPCs may overlap one crate, but not the other crate. To help with this, you can view what tiles have priority 1 set with the P1 button in the toolstrip. The blue tint covers all priority 1 subtiles.
### L1 Tileset
Select one or more tiles to draw from by dragging a selection boxaround them. Right-click the selection to apply a number of changes to the selected tiles ("Lock tileset editing" must be unchecked).
### L2 Tileset
Select one or more tiles to draw from by dragging a selection box around them. Right-click the selection to apply a number of changes to the selected tiles ("Lock tileset editing" must be unchecked).
### L3 Tileset
Select one or more tiles to draw from by dragging a selection box around them. Right-click the selection to apply a number of changes to the selected tiles ("Lock tileset editing" must be unchecked).
### Lock tileset editing
This should be checked when selecting tiles to draw to the map/image, to prevent accidental clicking/dragging a selection of tiles and unintentionally corrupting the tileset. Uncheck this only to manually edit one or more tiles in the tileset.
### Update
Applies all changes made in the graphics editor to the source's graphics.
### Auto-update
Automatically apply any changes made in the graphics editor to the source's graphics. If unchecked, click "Update" to apply the changes.

# HEX EDITOR
Shows the entire ROM in hexadecimal format in an interactive hex editor. Many editors have a button to open the hex editor and automatically jump to the location of the element index's data in the
ROM.
   
### Current ROM
Shows the current ROM, including all modifications done in all editors, before saving to disk.
### Original ROM
Shows the original ROM, since the last time it was loaded OR saved to disk.
### Goto Address
Type the address (in hexadecimal) and hit enter to jump to the address in the ROM data below.
### Search for value(s)
Search for one or more byte values (in hexadecimal) in the ROM. Hit enter to move through every search result.
### Decimal Value
Type a decimal value in here and it will automatically be converted to hex in the box on the right.
### Hexadecimal Value
Type a hexadecimal value in here and it will automatically be converted to decimal in the box on the left.
### Fill Selection
Fills a selection in the ROM data below with a single value (in hexadecimal).
### ROM Data
The raw ROM data as seen in a hex editor.
 
Change data here just as you would in a typical hex editor. Make selections by clicking and dragging the cursor over a series of bytes. Note that only selections smaller than the height of the window can be
made--such are the limitations of an amateur hex editor.

Copying, pasting, and deleting values is supported with the typical keyboard shortcuts or the respective buttons for such functions in the toolstrip at the top. You may undo or redo any changes made to the data as well.
### ROM Offsets
Offsets of each row currently visible in the ROM data box to the right. Each row is 16 bytes long.
