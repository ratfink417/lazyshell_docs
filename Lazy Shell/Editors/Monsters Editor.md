This editor includes all exclusively in-battle properties of monsters, including the battle scripts of each monster.
   
### Monster Index
Select the monster to load.
### Monster Name
The monster's displayed name when targetted.
### Effect Nullification
The effects that will have no effect if an effect-based attack is used on the monster, eg. Poison Gas (Poison), Terrorize (Fear), Bad Mushroom (Poison), etc.
### Element Weaknesses
The elements that will double the damage done to the monster by an element-based attack. These refer to magic- based attacks or items, such as Snowy (Ice) or Fire Bomb (Fire), eg. Fire Bomb will normally do 120 damage, but if used on a monster with a weakness for Fire it will double it to 240.
### Element Nullification
The elements that will have no effect if an element-based attack is used on the monster, eg. Ice Bomb and Snowy will have no effect on a monster with a nullification of Ice.
### Special Status
#### Invincible
will nullify all damage done to the monster, ie. all attacks, spells and items used on the monster will yield 0 damage.
####  Mortality Protection
will nullify all instant-death attacks such as Yoshi Cookie, Lamb's Lure, Geno Whirl, etc.
#### Disable Auto-Death
is for battle-script purposes. If checked, the monster will not be removed or set as defeated until manually removed through a battle-script command.
#### Share palette
is only used by the four crystals and its actual purpose is unknown.
### Flower Bonus
The Flower Bonus rewarded when the monster is defeated, based on the odds.
### Success%
The success rate that the Flower Bonus will be rewarded when the monster is defeated.
### Text View
Enable or disable text viewing in the psychopath message textbox. This is for easily identifying what the numerals in [] mean.
### Psychopath Message
Edit the monster's psychopath message. This is oriented exactly the same as battle dialogues, selecting from the same keystroke table and same list of 5 commands in the toolstrip to the right.
### Vital Status
#### HP
The monster's total hit points.
#### FP
The monster's total flower points.
#### Attack
The monster's attack power, ie. the base damage caused by the monster's non-magic-based attacks.
#### Defense
The monster's defense power, ie. the amount subtracted from the base damage of a non-magic-based attack on the monster.
#### Mg. Attack
The monster's magic attack power, ie. the base damage caused by the monster's magic-based attacks.
#### Mg. Defense
The monster's magic defense power, ie. the amount subtracted from the base damage of a non-magic-based attack on the monster.
#### Speed
The monster's speed, ie. the monster will have its turn before anyone else with a lower speed.
#### Evade%
The monster's evade percent, ie. the probability out of 100 a non-magic-based attack on the monster will miss. An evade% of 100 causes all non-magic-based attacks on the monster to miss. An evade% of 0 causes all non-magic- based attacks on the monster to hit. An evade% of 50 is a 50/50 equal chance that a non-magic-based attack on the monster will miss or hit.
#### Mg. Evade%
The monster's magic evade percent, ie. the probability out of 100 a magic-based attack on the monster will miss. An evade% of 100 causes all magic-based attacks on the monster to miss. An evade% of 0 causes all magic-based attacks on the monster to hit. An evade of 50 is a 50/50 equal chance that a magic-based attack on the monster will miss or hit.
### Rewards
#### Experience
The total experience gained from the monster when it is defeated. This is divided evenly among all active party members, ex. 500 experience points will be divided among 5 active party members as 100 points each.
#### Coins
The total coins gained from the monster when it is defeated.
#### Item (5%)
The item that has only a 5% chance of being won. If the 5% and 25% items are the same, then there is a 100% chance of the item being won, ie. it is always rewarded.
#### Item (25%)
The item that has a 25% chance of being won. If the 5% and 25% items are the same, then there is a 100% chance of the item being won, ie. it is always rewarded.
#### Yoshi Cookie
The item rewarded from the successful use of a Yoshi Cookie on the monster. The probability of a successful use is determined by the "Morph Success" (see below).
   
### Other Properties
#### Morph Success
The success rate of the Yoshi Cookie, Lamb's Lure and Sheep Attack items. 100% success rate means the item always works on the monster, 0% means the item never works on the monster.
#### Coin Sprite
The coin that shows when the monster is defeated. This property is ignored if the "Sprite Behavior" includes a "fade- out death".
#### Entrance Style
The behavior of the monster's initial animated entrance into battle. Although it is hardly noticeable, this might offset the exact initial coordinates of the monster in the formation by a couple of pixels.
#### Sprite Behavior
The various behaviors of the monster's sprite in battle. These include the sprite animations for the monster's death, its floating status, its common attack and defense animations, and more.
#### Strike Sound
The sound that plays when the monster does a common physical attack. Usually, but not always used.
#### Other Sound
The optional sound that can be used for less common physical attacks. These options are categorized by specific monsters, due to their limited usage among all monsters.
#### Elevate
The number of 16-pixel units a monster is raised above the ground.
   
# BATTLE SCRIPTS
A battle script is a set of commands which simply tell the monster what to do each turn. What spells or attacks it uses, under what conditions it uses them, etc. are all determined by a monster's battle script commands.
   
## Script Commands
The list of commands (aka "command tree") in the current script. Check the commands to delete, cut, or copy (using the toolstrip below), or double-click the commands to edit them in the box to the right.

## Command List
Select from a list of commands to add to the monster's battle script.

### Do
commands can either cast a spell or execute an attack on the current target. Either 1 specific spell/attack or 1 selected randomly from 3 are the options. Remember that if no target is set with the
### Target set
command, the monster will by default choose a random ally to attack.
### If
commands set a condition for all the following commands up to the closing "Wait 1 turn, return all" command. If the condition is met, the commands will execute; if not, the monster's turn is over and the script will start over from the beginning on the next turn.
### Memory
commands change the values and bits of the battle memory addresses 7EE000 to 7EE00F. These addresses are read by "If" commands for checking conditions.
### Run
commands will run a dialogue, event, or object sequence. An object sequence is selected from a list of animation scripts (roughly corresponding to the "Monster behaviors" in the animations editor) to playback for the monster.
### Target
commands set a number of attributes for a given target. Disabling/enabling a target will prevent/allow the player to target and thus attack the target.

## Insert Command
Insert the command after the currently selected command in the command tree.
### Apply Changes
Applies all change made to the currently edited command.
### Monster Image
Click/drag the cursor to set its upper-left distance from the monster sprite.
### Target X
The left distance, in 8x8 tile units, of the cursor from the monster's sprite.
### Target Y
The upper distance, in 8x8 tile units, of the cursor from the monster's sprite.
### Bytes Left
The remaining bytes available for all battle scripts.
### Hex
The raw hex data of the currently select command in the command tree.