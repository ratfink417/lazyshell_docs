Sprites are images representing all of the characters, monsters, items, objects, and some spell and attack effects. 

Sprite indexes can be viewed as 3 groups: 0 to 255 are primarily the allies, ally weapons, townspeople, and other common objects. 

256 to 511 are monsters, this order corresponding exactly to 0-255 in the monsters editor. 

512 to 767 are battle related sprites, like items or explosions. 

768 to 927 are spell and attack effects, and the rest are the end credit sprites.

This editor has 2 subwindows: molds and sequences. Each sprite has its own mold and sequence collections, both of these subwindows interacting with one another.

### Sprite Index
Select the sprite to edit by name. The name is based on a label assigned by the editor.
### Sprite Index
Select the sprite to edit by number.
### Image
The image # of the currently selected sprite refers to the set of properties that designate the raw graphics and palette set to use. Anything in the "IMAGE PALETTE..." and "IMAGE GRAPHICS..." panels are part of the sprite's image.
### Palette
The index of the palette in the palette set the sprite uses. This is mostly used for individual sprites that use the same image (thus, the same palette set) but have a different individual palette, such as the Sky Troopa and Malakoopa.
### Palette Set
The palette # the sprite's image's palette set begins at.
### BPP GFX Offset
The offset in the ROM (in hexadecimal) that the sprite's image's raw graphics begin. Increments by 0x20 because 4bpp 8x8 tiles are 0x20 bytes each.
### Animation
The animation # of the currently selected sprite refers to the set of properties that designate the sequences and molds to assign to the sprite. Anything in the "ANIMATION SEQUENCES..." and "ANIMATION MOLDS..." are part of the sprite's animation.
### VRAM Size
Larger VRAM values will allow more space for the sprite's raw graphics to be stored. Generally, the larger sprites such as Culex use larger values.
   
# MOLDS
A sprite mold is basically a single sprite image. Multiple molds can be accessed by the sequence data to create an animation sequence. 

Sprite molds, unlike effect molds, are drawn in two formats: gridplane and tilemap.

Gridplane arranges the 8x8 tiles used by the mold in a fixed table. Gridplane format molds are generally much smaller, with a limited dimension of 32x32, and a fixed position centered in the mold image box.
   
Tilemap format is composed of 16x16 tiles, each assigned a fixed coordinate and a set of 4 subtiles. This is relatively more common than the gridplane format, and far more versatile. 

The mold can be drawn using a collection of 16x16 tiles from the tileset provided on the right. Even external images can be imported as a tile or whole tileset.
   
### Mold Collection
The collection of molds used by the sprite's animation. A mold is a set of tiles arranged either dynamically or in a predefined grid to create a complete image that can be used by an animation sequence.
### Width/X coord
For gridplane format molds, this is the width, in 8x8 tile units, of the mold. For tilemap format molds, this is the absolute X coordinate of the 16x16 tile.
### Height/Y coord
For gridplane format molds, this is the height, in 8x8 tile units, of the mold. For tilemap format molds, this is the absolute Y coordinate of the 16x16 tile.
   
# SEQUENCES
Sequences are the animations a sprite uses. For monster sprites, the sequences are labelled differently to correspond to their use in battle. All other sprites are simply named with the format "Sequence #".
### Sequence Collection
The collection of sequences used by the sprite's animation. A sequence is a collection of frames, where each frame is assigned a mold from the mold collection above and a duration, creating an animation that can be played back in the image to the right.
### Frame Collection
The collection of frames used by the currently selected sequence at the left. Each frame is assigned a mold from the mold collection above and a duration, creating an animation that can be played back in the image to the right.
### Mold
The mold used by the currently selected frame. This value is based on its index in the mold collection above.
### Duration
The duration of the currently selected frame, or how long the frame will pause before the next frame starts. This value refers to the # of frames based on a 60-frames-per- second unit.
### Active
This must be checked for a sprite sequence to be usable. If not checked, the sequence data will save but not be accessible in game--or the next time the editor opens.