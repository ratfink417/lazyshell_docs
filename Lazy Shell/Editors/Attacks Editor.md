The attacks editor contains two subwindows: **spells**  and **attacks**
# SPELLS
The spells editor can modify all spell properties. These properties are applied to either in-battle usage, overworld usage or both. 

Spell #0-63 are ally spells, while all other spells are monster spells. Both are exclusively limited to usage by either allies or monsters. **Any attempts to assign monster spells to allies or vice versa will most likely cause a glitch, and is not recommended**

### Spell Index 
Select the spell to load.
### Icon 
The spell's icon as seen preceding its displayed name in all menus. Only ally spells have icons.
### Spell Name
The spell's displayed name in all menus.
### FP Cost
The amount of FP subtracted from the user's current FP when the spell is used.
### Magic Power
The base damage or heal amount caused by the spell.
### Hit Rate%
The spell's hit rate percent, ie. the probability out of 100 the spell will hit its target.
### Attack Type
The spell's attack type, ie. the spell will either cause damage or heal its target. This property can be ignored depending on the value of "Inflict Function".
### Effect Type
The effect type, ie. whether or not the spell will inflict or nullify (an) effect(s). Example: Poison Gas inflicts the Poison effect on the target(s) and Group Hug nullifies all adverse effects on the target(s). If set to {NONE} then anything checked under "Effect" is ignored. Likewise, this property is ignored if nothing under "Effect" is checked.
### Inflict Function
The inflict functions are specialized to certain spells, eg. "Scan/Show HP" is specialized to Psychopath and "Jump Power" is specialized to Jump. Some of these will cause the "Attack Type" to be ignored, ie. the spell will neither cause damage nor heal (eg. Psychopath).
### Inflict Element
The element assigned to the spell. If the target has a strength against the element, the base damage of the spell will be halved. If the target has a weakness against the element, the base damage will be doubled. If the target has a nullification property against the element, it will yield 0 damage.
### Other Properties
#### Check Caster/Target Atk/Def
will add to or subtract from the base damage or heal amount of the spell based on the target's attack and defense power instead of its magic attack and magic defense power. By default, no spells have this property enabled.
#### Ignore Target's Defense
will not subtract the target's magic defense power from the spell's base damage or heal amount (ie. the spell's magic power).
#### Check Mortality Protection
is redundant because the game engine always checks anyways. Only the dummied Knock Out spell has this enabled by default.
#### Usable in overworld menu
allows the spell to be used out of battle, ie. the overworld menu. This is normally reserved for healing spells. "9999 Damage/Heal" will kill the target in one strike, if the spell does not miss. Only the dummied Knock Out spell has this enabled by default.
#### Hide Battle Numerals
will hide the damage or heal amount total (ie. the numbers shown after an attack). This is generally used by spells that cause 0 damage and are only effect-based spells such as Sleepy Time, to avoid a redundant "0" appearing.

### Description
The description that appears in the lower-right corner of the overworld menu when the cursor is on the spell.
### Targetting
#### Other Targets
will limit the target to a single ally or enemy. This must NOT be checked with "Entire Party.
#### Enemy Party
will allow the spell to target the opposing party.
#### Entire Party
will cause the spell to target all members of either the ally party or enemy party. This must NOT be checked with "Other Targets".
#### Wounded Only
will limit the target to wounded members, ie. members with currently 0 HP.
#### One Party Only
will limit the target to only one party. By default, all usable spells have this property enabled. Uncheck at your own risk!
#### Not Self
will limit the target to other allies only, and the caster is untargettable. By default no spells have this checked, although the Mushroom item that turns the user into a mushroom has this property enabled.
### Status <. . . .>
The effect inflicted or nullified on a target, eg. Poison Gas inflicts Poison on a target, while Group Hug will nullify all effects a target is afflicted with except "Invincible". These properties are used based on the value for "Effect Type".
### Effect <. . . .>
The status of a target is either lowered or raised by 50%, depending on the value for "Effect Type". If the value for "Effect Type" is set to "Inflict" then the target's stats will be raised 50%. If "Effect type is set to "Nullify" then the target's stats will be lowered 50%.
   ### Example: 
   Geno Boost by default raises the target's Attack and Defense power by 50% (eg. if the attack and/or defense power of the target is 100, then it becomes 150). Shredder by default lowers the target's Attack, Defense, Magic Attack, and Magic Defense power by 50% (ie. it halves them).
### Timing Properties
#### Timing Frame Span
The # of frames from the start of the spell's animation when the user can trigger level 1 timing. The spell's damage will be increased by 50% if an ABXY button is pressed within this range. 
#### LV2 Timing START
The frame # from the start of the spell animation where the level 2 timing begins. Example: the default value for Jump is 39. This meansthat if an ABXY button is pressed after 39 frames have passed from thestart of the Jump animation (ie. when Mario jumps off the ground) the damage is increased by at least 100% (ie. doubled).
#### LV2 Timing END
The frame # from the start of the spell animation when the level 2 timing ends. Example: the default value for Jump is 44. This means that if an ABXY button has NOT been pressed after 44 frames have passed from the start of the Jump animation (ie. when Mario jumps off the ground) the opportunity to increase the damage by 100% (ie. doubled) is gone.
#### LV1 Timing END
The frame # from the start of the spell animation where the level 1 timing ends. Example: the default value for Jump is 45. This means that if an ABXY button has NOT been pressed after 45 frames have passed from the start of the Jump animation, the opportunity to time the attack for any damage increase is gone.
#### Level 2 Frame
The frame # from the start of the spell animation when, if the button is held to this point, the damage is increased by at least 50%. This is by default around when the first red star appears on screen.
#### Level 3 Frame
The frame # from the start of the spell animation when, if the button is held to this point, the damage is increased by at least 75%. This is by default around when the second red star appears on screen.
#### Level 4 Frame
The frame # from the start of the spell animation when, if the button is held to this point, the damage is increased by at least 100%. This is by default around when the third red star appears on screen.
#### Charge Overflow
The frame # from the start of the spell animation when, if the button is held to this point and beyond, the damage "overflows" and is reset to the base value, ie. no damage increase.
#### Orb Frame Span
The "speed" of the firing, or the # of frames the player must wait between button presses in order to "fire" another fireball. NOTE: values less than the default may cause the game to freeze if the button is consistently pressed for each frame span between fireballs.
#### Maximum Orbs
The maximum number of orbs the player can fire before the spell is over. The accumulative damage is increased with each fireball, so lowering/raising this value will affect the maximum accumulative damage as well.
#### Timing Frame Start
The frame # from the start of the spell animation when the player has the opportunity to rotate the directional pad to increase damage.
#### 1/4 Rotations
The maximum number of quarter rotations (a quarter rotation would be, for example, from DOWN to DOWN-LEFT to LEFT) allowed to increase damage. Raising/lowering this value will affect the maximum accumulative damage.
#### Maximum 
The maximum number of times the player can execute another "jump" or "star rain" by timing it. Values above 127 will likely cause anomalies (ie. the spell caster might only be able to do 13 jumps, even if the maximum is set to 200 for example).
#### # 
The instance selected. The rest of the instances have the same "Instance Frame Duration" as the last one in the list of instances. For example, Super Jump instances 14 through 199 will have the same "Instance Frame Duration" as instance 13. NOTE: star rain's "Instance Frame Duration" is the same for all instances, so there isn't a list for them.
#### Frame Span
The # of frames before either Mario or the Star lands on the target that the player is able to time the spell to increment damage and allow another instance to be timed. NOTE: star rain's "Instance Frame Duration" is the same for all instances, so there isn't a list for them.
#### Maximum power-ups
The maximum number of times the player can press an ABXY button to increase damage during the spell animation.
# ATTACKS
Attacks used by monsters can be modified in the attacks editor on the right. These are all exclusively in-battle monster attacks. Many monster attacks have no name, and even if given one it will not be displayed because the attack animation code does not enable it. Several attacks are unlabelled and distinguishable only by their appearance and what uses them.

### Attack Index
Select the attack to edit by number.
### Attack Name
The attack's name displayed at the top of the screen when executed by the monster. Many monster attacks have no name, and even if given one it will not be displayed because the attack animation code does not enable it.
### Hit Rate%
The attack's hit rate percent, ie. the probability out of 100 the attack will hit its target.
### Attack Level
The attack level multiplies the base damage of the attack (ie. the monster's attack power) by a number.
	An attack level of 0 will yield base damage. 
	An attack level of 1 will multiply the base damage by 1.5. 
	An attack level of 2 will multiply the base damage by 2. 
	An attack level of 3 will multiply the base damage by 4. 
	An attack level of 4 will multiply the base damage by 8. 
	An attack level of 5 will multiply the base damage by 16. 
	An attack level of 6 will multiply the base damage by 32. 
	An attack level of 7 will multiply the base damage by 64.
 
#### **Example:** 
if the monster's attack power is 6, and the attack level of the attack is 7, then the damage will be increased to 384 (ie. 6 x 64).
### Effect Inflict
The effect inflicted on a target, eg. S'crow Bell inflicts Scarecrow on a target, Thornet inflicts Poison, etc.
### Status Up
The status of a target is raised by 50%.
	Example: Valor Up by default raises the target's Defense and Magic Defense power by 50% (eg. if the magic defense and/or defense power of the target is 100, then it becomes 150). Vigor up! by default raises the Magic Attack and Attack power by 50%.
### Attack Type
#### 9999 Damage
will kill the target in one strike, if the attack does not miss.
#### No damage
will yield 0 damage to the target (both "No damage" properties are exactly the same, but different bits).
#### Hide Battle Numerals
will hide the total damage (ie. the numbers shown after an attack). This is generally used by attacks that cause 0 damage and are only effect-based attacks such as S'crow Bell or "9999 damage" enabled attacks such as Scythe, to avoid a redundant "0" or "9999" appearing.