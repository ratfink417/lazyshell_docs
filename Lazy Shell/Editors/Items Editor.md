# ITEMS
Items include both items usable in battle and the overworld menu, as well as all forms of equipment and special items. Their properties are applied to either in-battle usage, overworld usage or both.

### Item Index
Select the item to load.
### Item Name
The item's displayed name in all menus.
### Icon
The item's icon as seen preceding its displayed name in all menus.
### Coin Value
The amount the item costs in a shop. Final costs varies depending on the "Purchase Discounts" properties of the shop selling the item. The resale value of the item is exactly half the "Coin Value" (ie. how many coins you receive from selling it in a shop). NOTE: to make item a "Special Item", set coin value to 0.
### Speed
The wearer's total speed is increased by this amount. This property is ignored for non-equipment items.
### Attack Range
The attack range is the range of damage, plus and minus the "Attack" value, done to the target. The final damage will be a random value chosen from the "Attack" value plus and minus the "Attack Range" value.

Example: if the "Attack" is 50, and the attack range is 25, the final damage could be anywhere from 25 to 75. This property is ignored for non-weapon items.
### Infliction Amount
The exact damage, heal or increment amount inflicted by an item. This property will heal, damage or increment a property depending on the value of "Inflict Function". 

Example: Flower Box has an "Infliction Amount" of 5 and an "Inflict Function" of Raise Max FP, which means it increments the Max FP by 5. Ice Bomb has an "Infliction" "Amount" of 140, which means it does 140 base damage.
### Attack
The wearer's total Attack Power is increased by this amount. This property is ignored for non-equipment items.
### Defense
The wearer's total Defense Power is increased by this amount. This property is ignored for non-equipment items.
### Magic Attack
The wearer's total Magic Attack Power is increased by this amount. This property is ignored for non-equipment items.
### Magic Defense
The wearer's total Magic Defense Power is increased by this amount. This property is ignored for non-equipment items.
### Item Type
The type of item will determine whether the item can be equipped, what menu inventory it appears in, etc.
### Effect Type
The effect type, ie. whether or not the item will inflict, nullify or protect against (an) effect(s).

#### Protection
should only be used for equipment, such as the Super Suit which protects against all adverse effects.
#### Infliction
will inflict anything under "EFFECT" on the target, or raise any stats under "STATS". Set only for items that are used in battle.
#### Nullification
will remove the effects under "EFFECT" on the target, or lower the stats under "STATS". Set only for items that are used in battle.

If set to {NONE} then anything checked under "EFFECT" and "STATUS" is ignored. Likewise, this property is ignored if nothing under "EFFECT" and "STATUS" is checked.
### Inflict Function
The inflict function is only used for non-equipment items, such as the Mushroom which is set to "Restore HP" and Maple Syrup which is set to "Restore FP", or the Flower items that raise the maximum FP are set to "Raise Max FP". Some functions read the "Infliction Amount" value to determine how much HP, FP, etc. will be restored/raised.
### Inflict Element
The inflict element is only used with items that typically cause damage to the target. By default, only the Fire and Ice Bomb items have this set, although any item that can cause damage will read from this.
### Item Properties

#### Mortality Protection
is only used with equipment and causes all instant death attacks to always miss.
#### Hide Battle Numerals
is only used with items in battle, typically those that cause 0 or 9999 damage to avoid the redundant "0" or "9999" appearing.
#### Usable in Battle Menu
and "Usable in Overworld Menu" indicate whether the item can be used in and/or out of battle in the menu.
#### Reusable
gives the item infinite usage, eg. the "Star Egg" can be used repeatedly and never run out. 

 NOTE: the Lucky Jewel can has this set, but the CPU reads a RAM address to limit the usage to 10 times. That cannot be changed here.
### Description
The item description as it appears in the lower-left corner of the overworld menu when the cursor is on the item.
### Effect <. . . .>
The effect inflicted, protected against or nullified on a target. 

Example: Red Essence inflicts Invincible on the target. Super Suit protects against all effects (except Invincible). Able Juice nullifies all effects (except Invincible). These properties are used based on the value for "Effect Type".
### Element Nullification
All attacks with the following checked elemental properties will always cause 0 damage to the wearer of the item. This property only applies to equipment.
### Element Weaknesses
All attacks with the following checked elemental properties will double the damage to the wearer of the item. This property only applies to equipment.
### Status <. . . .>
The status of a target is either lowered or raised by 50%, depending on the value for "Effect Type". If the value for "Effect Type" is set to "Infliction" then the target's stats will be raised 50%. If "Effect type" is set to "Nullification" then the target's stats will be lowered 50%.

Example: Power Blast by default raises the target's Attack and Magic Attack power by 50% (eg. if the attack and/or defense power of the target is 100, then it becomes 150). If the item is equipment, then the wearer's stats (in-battle) will be raised/lowered 50%. If the item is a usable item in- battle, then the target's stats will be raised/lowered 50%.
### Who Can Equip
Who can equip the item. Example: Lazy Shell can be equipped by all 5 characters. This property is ignored by non-equipment items.
### Targetting
#### Other Targets
will limit the target to a single ally or enemy. This must NOT be checked with "Entire Party".
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

NOTE: these properties are ignored by items that cannot be used in battle.
### Menu Cursor Lead To
The action of the cursor when the item is selected for use in the overworld menu only. Example: the Mushroom will direct the cursor to HP (ie. the HP will be restored) and the Maple Syrup will direct the cursor to FP (ie. the FP will be restored).
### Menu Cursor Limitations
"Restore only if HP less than max" will restore the HP only if the target's current HP does not equal the maximum HP. "Restore only if FP less than max" likewise, does similarly for FP.

# Weapon Timing
#### [1.5x]
The frame # from the start of the weapon animation (ie. the time the character runs up to the target and starts wielding the weapon) where the level 1 timing begins. Example: the default value for Hammer is 8. This means that if an ABXY button is pressed after 8 frames have passed from the start of the Hammer animation (ie. when Mario starts to lift the hammer) the damage is increased by at least 50%.
### (2x]
The frame # from the start of the weapon animation (ie. the time the character runs up to the target and starts wielding the weapon) where the level 2 timing begins. Example: the default value for Hammer is 14. This means that if an ABXY button is pressed after 14 frames have passed from the start of the Hammer animation (ie. when Mario starts to lift the hammer) the damage is increased by at least 100% (ie. doubled).
### 2x)]
The frame # from the start of the weapon animation (ie. the time the character runs up to the target and starts wielding the weapon) where the level 2 timing ends. Example: the default value for Hammer is 20. This means that if an ABXY button has NOT been pressed after 20 frames have passed from the start of the Hammer animation (ie. when Mario starts to lift the hammer) the opportunity to increase the damage by 100% (ie. doubled) is gone.
### 1.5x]]
The frame # from the start of the weapon animation (ie. the time the character runs up to the target and starts wielding the weapon) where the level 1 timing ends. Example: the default value for Hammer is 38. This means that if an ABXY button has NOT been pressed after 38 frames have passed from the start of the Hammer animation (ie. when Mario starts to lift the hammer) the opportunity to time the attack for any damage increase is gone.

# SHOPS
Each shop is a collection of items which appear when a shop menu is opened up, and a set of properties which affect the price and availability of the item in the collection.

### Shop Index
The shop to edit by label. These shop "names" are simply labels used to identify the shops. The user may change the label.
### Shop Label
The currently selected shop's label. Use this to label / identify a shop. This is not read from anywhere in the ROM and is exclusively part of the editor. Changing this will have no effect on the game.
### Shop Options
#### Buy with Frog Coins, one product each
is used, for example, by the "Frog Disciple" in Seaside Town. Only one of each product can be bought with Frog Coins only.
#### Buy with Frog Coins
is the same as above, only the product(s) can be bought as many times as afforded. The "Frog Coin Emporium" uses this property.
#### Buy only, no selling
is obvious: only buying is allowed in the shop, and items cannot be sold. Both of these properties are exactly the same, there is no difference (they are merely two separate bits that each have the same property).
### Purchase Discounts
These will lower the prices of the items being sold, according to their "Coin Value". For example, a Juice Bar has a discount of 50%, which means the KeroKeroCola it sells (which is normally 400 coins) is 50% less than 400 coins, ie. 200 coins. These can be combined, ie. if 50% and 25% are both checked, then the discount is 75%.
