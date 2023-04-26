The 7 different areas of the world map in SMRPG can be edited. 

Each world map image is a tileset, like battlefields, and are modified in the same manner. 

Unique features of the world maps include a location set, a banner, and a mode 7 transformation as seen in-game. 

A separate layer for the banner displaying the location's name. This and the locations can be shown or hidden with a button.
   
### World Map Index
Select the world map to load. There are 8 maps total. The map may appear disoriented in correlation with the locations, because the game engine stretches the map.
### Show Locations
Show or hide the locations in the image below. If the lo- cations are shown, they can be clicked to edit them in the "Location Properties" box below.
### Locations
The total # of locations that the current map uses. The collection of locations used by the map is based on the locations used by the earlier maps. 

Map #0, for example, by default uses 7 locations total, and since it is the first map that means it will use locations #0 - 6 (as seen in the "LOCATIONS" editor panel). Map #1 uses 6 locations, and because the last location in Map #0 is location #6, then Map #1's locations will be locations #7 - 12 (ie. 6 total, starting at #7).
### Tileset
The tileset, or the actual image used by the map. To edit a tile in the tileset, click on the tile in the image above to edit it in the "WORLD MAP TILE EDITOR" panel to the right.
### X
The X coordinate of the map.
### Y
The Y coordinate of the map.

# Locations
A location set, or collection of locations which lead to a level or another location, is included in each world map. When the locations are toggled on, the map image transforms to comply with the mode 7 transformation applied by the game. In order to provide accurate coordinates for the location points the image must be drawn this way in the editor.
### Location Index
Select the location to load. If the location is in the currently selected world map, then it will be highlighted in the map.
### Location Name
Edit the location's name, as it appears at the bottom of the screen when the Mario sprite is over the location.
### X
The absolute X coordinate of the location.
### Y
The absolute Y coordinate of the location.
### Memory Address
If the bit (under "BIT SET") of this memory address is set, then the location is enabled / visible in-game.

Example: by default location #9 (Mushroom Way) is not enabled or visible until bit 2 of memory address $7065 is set. This bit is set at the end of event script #1396. These bits are always set in an event script.
### Bit
If this bit of a memory address (under "IF MEMORY") is set, then the location is enabled / visible in-game.

Example: by default location #9 (Mushroom Way) is not enabled or visible until bit 2 of memory address $7065 is set. This bit is set at the end of event script #1396. These bits are always set in an event script.
### Location
If this is enabled, the destination will be another location (typically a location in different one of the 8 maps). If not enabled, then an event (Run Event) will be triggered.
### Memory Address
If the bit (at the right) of this memory address is set, then the location will lead to the first destination (next to "lead to destionation"), otherwise it will lead to the second one. This is ignored if "LOCATION" is disabled.
### Bit
If this bit of the memory address (at the left) is set, then the location will lead to the first destination (next to "lead to destionation"), otherwise it will lead to the second one. This is ignored if "LOCATION" is disabled.
### Assigned event #
The event to run when entering the location. This is ignored if "LOCATION" is disabled.
### Edit
Edit the assigned event # in the Events editor.
### Lead to destination
The destination the location leads to.
### Else lead to destination
The alternate destination the location leads to, if a memory's bit is not set. This is ignored if "LOCATION" is disabled.
### East
Enable the eastern path of the location, or the path to the location the Mario sprite moves to when RIGHT is pressed on the d-pad.
### South
Enable the southern path of the location, or the path to the location the Mario sprite moves to when DOWN is pressed on the d-pad.
### West
Enable the western path of the location, or the path to the location the Mario sprite moves to when LEFT is pressed on the d-pad.
### North
Enable the northern path of the location, or the path to the location the Mario sprite moves to when UP is pressed on the d-pad.
### East location
The location the eastern path leads to, or the location the Mario sprite moves to when RIGHT is pressed on the d-pad.
### South location
The location the southern path leads to, or the location the Mario sprite moves to when DOWN is pressed on the d-pad.
### West location
The location the western path leads to, or the location the Mario sprite moves to when LEFT is pressed on the d-pad.
### North location
The location the northern path leads to, or the location the Mario sprite moves to when UP is pressed on the d-pad.
### Open eastern path if memory set
If the bit (at the right) of this memory address is set, then the eastern path will be open.
### Open southern path if memory set
If the bit (at the right) of this memory address is set, then the southern path will be open.
### Open western path if memory set
If the bit (at the right) of this memory address is set, then the western path will be open.
### Open northern path if memory set
If the bit (at the right) of this memory address is set, then the northern path will be open.
### Open eastern path if bit set
If this bit of the memory address (to the left) is set, then the eastern path will be open.
### Open southern path if bit set
If this bit of the memory address (to the left) is set, then the southern path will be open.
### Open western path if bit set
If this bit of the memory address (to the left) is set, then the western path will be open.
### Open northern path if bit set
If this bit of the memory address (to the left) is set, then the northern path will be open.