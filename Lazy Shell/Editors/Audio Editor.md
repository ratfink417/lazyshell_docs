Two subwindows are included in this editor: the samples and SPC editors.
# SAMPLES
A sample is simply a raw audio sound that the SPCs use during playback. It is NOT to be confused with a sound effect like Mario's jump: it should be viewed as a single instrument sound used by songs and sound effects. It is compressed in BRR format, the traditional SNES format for audio samples. The first 16 samples are used primarily by the SPC sound effects (ex: Mario's jump). The remaing samples are all instruments used almost exclusively by SPC Music Tracks.

## Sample Index
Select the sample to load.

## Relative Frequency
This is used to tune a sample sound to the pitch of A. Relative frequency is the frequency of the sample in distance by hertz from a base 32000hz. The difference, however, is not a simple matter of addition/subtraction. The formula for calculating final frequency is as follows:
	- If the relative frequency is positive: 32000 x 2^(RelFreq / 256 / 12).
	- If the relative frequency is negative: 32000 / 2^(RelFreq / 256 / 12).
 So multiply or divide 32000 by 2 to the power of the final quotient of what's between () to get the final frequency of the sample.
 
## Relative Gain
Simply put: the volume change from the base volume.
 
## Loop Start
If the sample loops this is the location in bytes it loops back to. If set to 0 or a value higher than the BRR sample's total size in bytes, it loops back to the beginning. This value must point to the start of a chunk, in other words it must be divisible by 9--the size of each chunk in a BRR sample's data. The loop start point is indicated in the wavelength image by a vertical gray line.

# SPCS
Three types of SPCs exist in SMRPG: SPC Music Tracks, Event Sound FX, and Battle Sound FX.
 
## SPC Type
Select the type of SPC to load.
 
## SPC Index
Select the SPC to load.
 
## Instruments
A collection of instruments used by the SPC. Only music tracks can have a collection of instruments, up to 20 maximum. Each instrument is assigned a sample and base volume. Remember that the instruments assigned in the track commands must be in this collection, otherwise they'll be muted. Changing an instrument in this list will automatically synchronize all sample set commands in the channel tracks that use the instrument's sample. Thus manual updating in the track editor is unnecessary.
 
## Delay Time
Higher values set greater distances between each echo.
 
## Decay Ratio
Higher values create a longer lasting echo.
 
## Echo Volume
The intensity, or strength, of the echo. Higher values mean stronger echoes.
 
## Percussives Collection
The percussives collection is a collection of percussive instruments, each assigned a sample, pitch, volume, and a different pitch index. Since there are only 12 pitches (C to A#) only up to 12 percussives can logically be used, and all 12 must have different pitch indexes.
 
## Pitch Index
This is not the actual pitch of the percussive (which is below) but the pitch index assigned to it. If a channel is in percussive mode, then the notes will play an instrument in the percussive list based on the note's pitch corresponding to the percussive's pitch index.

### Example:
if a percussive has a pitch index of B, then for any B notes played while in percussive mode it will play that percussive's sample. All percussives in the collection must have different pitch indexes.
 
## Pitch
Whenever a percussive is played, this is the fixed pitch it will play at. The percussive's pitch cannot be changed during the song. If you want to play the same percussive instrument at different pitches, you must have more than one percussive in the collection with the same sample but different pitch index.
 
## Volume
Base volume of the percussive.
 
## Speaker Balance
The percussive's balance between the two speakers.
 
## Select Command
Select from a list of SPC commands to insert, with the button on the right.

# SPC Music Tracks
SPC music tracks are the songs used in the game. The instruments box contains a list of instruments which are given a sample and a base volume. These are the instruments accessed by the track data to play back the sequence of notes heard in a song. Any instrument which accesses a sample index higher than 15, however, must be set in a channel and must be in this list to be heard at all, therefore changing an instrument in the track editor box to the right to an instrument NOT in this box will create nothing but silence for that channel.
# Sound FX
Event and battle sound effects use the exact same types of commands as SPCs, except they only use two channels (6 and 7), have no instrument or percussive collections and can only use samples 0-15 with some exceptions. Those exceptions are if a sample index higher than 15 is set in a sound effect's track data, that instrument must be in the currently playing song's instrument collection to be heard at all. Examples include the Tadpole Pond steel drum note sounds on the staff, or jumping on the organ in the sanctuary.

# Channel Tracks
Channel track commands, in simple terms, are the notes and note properties of a song. They are displayed on a channel-by-channel basis in the channel track editor. Music tracks can have anywhere between 0 and 8 active channels, while sound effects only two. Channels run in syncronization with one another. Each channel's commands run in straight line, in similar nature to the commands in other script editors.

# Score Viewer
The score viewer, only functionable with the music tracks, displays the channel tracks in notation form.

Notes and rests can be clicked to jump to the corresponding command in the track editor on the right. 

Sample and percussive mode changes are indicated by icons, and notes in percussive mode are identifiable by the x note heads. 

Staff attributes like time signatures, note spacing, and others are user-defined but do not affect the ROM if modified. 

Repeats viewable in the track editor are not incorporate in the score viewer (ie. no repeat bars), so a sequence of notes within a repeat loop is simply drawn multiple times.

## Staff Height 
Change the height of the staffs in the score viewer, in pixels. Use larger values to view notes beyond the visible bounds.

## Time Signature beats per measure
In the traditional manner of time signatures, this is the number of beats per measure.

## Time Signature
note value The note value is the beat length of each note. A time signature of 3/8 means a measure's length is equivalent to three 8th notes. 13/4 is thirteen quarter notes per measure. The measure lines in the score view are drawn based on these values.

## Note Spacing % 
The spacing between each note by %. Each type of beat has a number of default ticks. A whole note is 192 ticks, so the score viewer sets the distance from a whole to 192 pixels. A quarter note is 48 ticks, thus quarter notes are 48 pixels apart. Changing the note spacing to 50% for example would draw a distance of 96 pixels between whole notes and 24 pixels between quarters.

## Show Rests 
Show or hide the rests, if they are cluttering up the staff and obstructing the view.

# Score Writer
Write your own basic scores using the notes and rests provided in the toolstrip. 

This is completely separate from the ROM, and does not interact with the ROM in any way other than to export the custom made score to separate .txt files for each channel and import those into an
SPC's channel track.

Notes/rests can be drawn, erased, and the orientation can be changed in the same nature as the score viewer (staff height, time signature, etc). This is a fairly basic feature, which can only insert the beats used by SMRPG and no notes with a fixed durations/tick length. 

Most useful is its ability to undo/redo any action and save/export in three formats.

# BATTLEFIELDS
A battlefield is simply a background image used in a battle. More technically, it is a tileset and NOT a tilemap: it contains only one layer and is arranged on an 8x8 tile basis. Battlefields can have between 1 and 4 quadrants, most of which only have 1.
   
## Battlefield Index
Select the battlefield to load.

**GFX Set 1:** The 1st graphic set in the current battlefield.
**GFX Set 2:** The 2nd graphic set in the current battlefield.
**GFX Set 3:** The 3rd graphic set in the current battlefield.
**GFX Set 4:** The 4th graphic set in the current battlefield.
**GFX Set 5:** The 5th graphic set in the current battlefield.
**Tileset:** The tileset used by the current battlefield.
**Palette Set:** The palette set is a set of 7 palettes that comprise all of the colors that the battlefield image uses.