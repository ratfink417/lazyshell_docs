The spell effect editor has two subwindows: molds and sequences. A spell effect is not the entire spell animation itself, but an animation sequence used in spell animations. Spell animation scripts can use more than one different spell effect, for example, the "Boulder" spell uses spell effect 26 (boulder) and 53 (black flash).

### Effect Index
Select the spell effect to load.
### Image
The image # of the currently selected spell effect refers to the set of properties that designate the raw graphics and palette set to use. Anything in the "Image Properties" box is part of the spell effect's image.
### Palette
The index of the palette in the palette set the spell effect uses. This is mostly used for individual spell effects that use the same image (thus, the same palette set) but have a different individual palette, such as the star rain and black star rain.
### X
The X shift is the number of pixels to shift the spell effect animation to the left.
### Y
The Y shift is the number of pixels to shift the spell effect animation up.
### Palette Size
The size of the palette in bytes. The total number of palettes in the spell effect image's palette set equals the size divided by 32.
### Graphic Size
The size of the raw graphics in bytes (hexadecimal). Every 0x20 bytes is one or two 8x8 tiles.
### BPP Codec
The codec refers to how the graphics are read by the game engine. 4bpp uses up to 16 colors total, while 2bpp only uses 4 colors total.
   
# MOLDS
Effect molds are basically a collection of tilemaps, each drawn from the same tileset (on the right) much in the same nature as levels, although just one layer.

### Width
The width of the spell effect's animation molds, in 16x16 tiles.
### Height
The height of the spell effect's animation molds, in 16x16 tiles.
### Size
The size of the tileset in hexadecimal bytes. The total number of tiles in the spell effect image's tileset equals the size (in hexadecimal) divided by 8.
### Mold Collection
The collection of molds used by the spell effect's animation.

# SEQUENCES
Each effect can have only one sequence, unlike sprites, and is a collection of frames. Each frame is assigned a mold from the mold collection above and a duration, creating an animation that can be played back in the image to the right.

### Frame Collection
The collection of frames used by the spell effect animation.
### Mold
The mold used by the currently selected frame. This value is based on the collection of molds in the molds editor above.
### Duration
The duration of the currently selected frame, or how long the frame will pause before the next frame starts. This value refers to the # of frames based on a 60-frames-per- second unit.