Dialogues are the game's script. Dialogues must be triggered by an event script command to show. Generally, most dialogues are "assigned" to an NPC, ie. the NPC has an event # assigned to it, wherein there is a command to display a specific dialogue # in that event script. The first few dialogues are by default used as the message / caption that is shown at the top of some levels. To find a dialogue, use the text field "Find...". Dialogues have a number of commands and characters which can be inserted either using the toolstrip on the right or through font table's right-click menu item "Insert into dialogue". The dialogues editor contains two subwindows: battle dialogues and fonts.
   
## Dialogue Index
Select the dialogue to edit by number.

## Text View
Enable or disable text viewing in the dialogue textbox. This is for easily identifying what the numerals in [] mean.

## Dialogue
Edit the current dialogue. To insert symbols, simply right-click the symbol in the dialogue font table and click "Insert into dialogue".

## Compression Table
A compression table is a set of texts which are assigned a single byte when saved to ROM to conserve dialogue space. These are typically the most common words or parts of words present in all dialogues, hence saving the most space possible. Beware that changing these may either increase or decrease the number of free bytes. Unless translating to another language, it's best not to change any of these except for the last two labelled "Booster".

# BATTLE DIALOGUES
Battle dialogues are single-line texts displayed only in battle, and must be triggered by a battle script or animation script command to be shown. They use the same "dialogue" font table as the main overworld dialogues, but have a limited number of non-symbol related commands, however, compared to the overworld dialogues. These commands can be inserted with toolstrip on the right, while special symbols are insertable using the font table's right-click menu.

## Battle Dialogue Index
Select the battle dialogue to edit by number.

## Battle Dialogue
Edit the current battle dialogue. To insert symbols, simply right-click the symbol in the font table and click "Insert into battle dialogue". Symbols can be manually defined in the text using [] brackets, wherein the symbol's index in the font table is placed.
   
# FONTS
4 font tables can be selected:
## Menu
font is used in the overworld menu.
## Dialogue
font is used in overworld and battle dialogue.
## Description
font is used in item and spell descriptions in the overworld menu.
## Triangles
are the option triangles used in overworld dialogue. It must be noted that each font table has its OWN keystroke table. If you are translating the game's text, remember that if writing special characters like á, é, etc. into an element's name, description, etc. you must assign a keystroke value to the font letter you want to associate it with--for ALL three font tables. Only the "dialogue" font allows the user to insert symbols into the overworld or battle dialogue through the right-click menu.

### Font Table
Select the font table to load.
### Width
The width of the character, in pixels, as drawn in-game. Pixels beyond the boundaries of the width will NOT display in the dialogue.
### Font Table
Click a character to edit it in the paint box on the right.
### Width
The width, in pixels, of the font letter.
### Key
The key assigned to the font letter. If drawing letters with accents, diacritic marks, etc. change its key to that letter before beginning a translation.
