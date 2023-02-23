# garhis-custom-foundry-stuff
A module for FoundryVTT containing custom items, spells, features, and journal entries

## Current Items and Instructions on their use

### Garhi's Descriptions Compendium
Contains journal entries linked to by the Signature Items giving more detailed descriptions of the current and potential abilities

### Garhi's Macro Compendium
Contains macros necessary for some of the item's effects to properly function. These must be imported in to the world as world macros.

### Garhi's Actors Compendium
#### Testing Dummies (Various actors for use in developing and testing new items and effects, not meant for use in games)
#### Invulnerable Summons (These actors are all flagged Invulnerable to Damage and Conditions)
Cloud of Daggers - A Medium sized Token with no meaningful effects or attacks unless spawned by the matching spell in the Items Compendium.
Spiritual Weapon - A Medium sized Token with no meaningful effects or attacks unless spawned by the matching spell in the Items Compendium.
Blaze Canister Patch - A medium sized token with an aura with a radius of 2 feet, all creatures in the aura take 2d4 fire damage at the start of their turn.
Patch of Twilight Flames - A medium sized token with an aura with a radius of 2 feet, all creatures in the aura take 1d8 radiant damage at the start of their turn.


### Garhi's Items/Features/Spells Compendium
#### Base/Shared
##### Features
[[TODO: Careful Spell, Familiar Help Action, Mind Sharpener]]
Twilight Sanctuary - Places an effect on the caster that generates an aura with a 30 foot radius. Each friendly creature in the aura will heal for 1d6+Caster's Cleric Level Temporary Hit Points at the end of its turn. Also generates a Sequencer visual effect matching the size of the aura.
Emboldening Bond - Places an effect on targeted creatures granting a Midi Optional effect for 10 minutes. This effect will prompt the player on each attack/ability/skill/save to add 1d4 to the roll. Once used, it will no longer prompt until the next turn. If players don't wish to use it to save it for a possibly more useful roll later int he turn, they need to exit out of the dialog window by the X in the corner.
War Caster - Applies a passive effect on the actor granting advantage on concentration checks.
Gunner/Crossbow Expert - Applies a passive effect that ignores disadvantage imposed on ranged attacks by nearby enemies. Only important if "Ranged attacks when a foe is closer than this have disadvantage" is set in Midi-Qol Rules configuration.
Great Weapon Master - When used applies a temporary buff to the caster that adds a -5 penalty to attack and a +10 bonus to damage for the next attack made. Must be cast before each attack the player wants to apply it to.
Sharpshooter - As Great Weapon Master, but also applies a passiave buff to the Actor that removes disadvantage when attacking at Long Range. Only important if "Check weapon range when attacking" is enabled in Midi-Qol Mechanics configuration.
Fighting Spirit - When cast heals the caster for 5 temporary hitpoints, and applies an effect granting advantage on all attacks made until the end of the turn. Needs to be manually updated for a higher level fighter to heal the appropriate temporary hitpoints.
Bladesong - When cast applies an effect to the caster granting Bladesong's bonuses for 60 seconds/10 rounds. Properly pulls form the Intelligence ability mod to apply the AC and Concentration save bonuses.
Steady Aim - When used applies two effects to the caster. The first grants advantage to the next attack roll made, the second reduces all movement speeds to 0 until the end of the turn.
Sneak Attack - Applies a passive effect to the actor that prompts them to use sneak attack on each valid successful attack. Stops prompting once used until the end of the turn. Can be manually clicked to roll sneak attack damage.
Starlight Step - Functions as Misty Step, prompting the player to select a space within range to teleport to.
Blessing of the Raven Queen - Functions as Misty Step, prompting the player to select a space within range to teleport to. Also applies an effect to the castor granting resistance to all damage until the start of their next turn.
Protective Bond - Functions as Misty Step, prompting the player to select a space within range to teleport to.

##### Spells
[[TODO: Hex]]
Absorb Elements - When cast, prompts the player to select which damage type is being absorbed. Applies two effects to the caster, the first grants Resistance against that damage type until the start of their next turn. The second grants a spell-level based damage bonus to the next melee attack made before the end of their next turn.
Aid - Applies an effect to targeted creatures increasing their maxhp for 8 hours. Then heals them for the same amount.
Aura of Vitality - Simply places an effect on the caster for 60 seconds/10 rounds, meant as a duration tracker.
Aura of Vitality Pulse - At-Will spell that heals for 2d6 hitpoints. Roll this to actually heal while Aura of Vitality is active.
Booming Blade - Places a buff on the caster that causes the next melee attack made before the end of the turn to do extra thunder damage. Correctly pulls from character level to determine the damage and interacts with the BoomingBladeItemMacro to apply the Thrumming Effect to the target.
Cloud of Daggers - Spawns a token from the actor named "Cloud of Daggers" and places it on the canvas. Applies an aura to that token that will dead Spell level appropriate slashing damage to targets in range on the start of their turn. Also sets the damage of Cloud of Daggers Slash to the appropriate number of dice for the level of the spell cast.
Cloud of Daggers Slash - Meant to be updated by Cloud of Daggers and then used manually when creatures enter into the aura for the first time on a turn.
Detect Magic - Plays an animation and then applies an effect and a sequencer aura to the caster for ten minutes.
Green-Flame Blade - Places a buff on the caster that causes the next melee attack to deal additional fire damage. The amount of damage is correctly set based on the caster's character level.
Green-Flame Blade Splash - Meant to be manually rolled against the splash target after successfully hitting with Green-Flame Blade.
Hold Person - Applies an effect on targets that fail the save that applies the Paralyzed Condition. Automatically prompts for a repeated saving throw at the end of their turn, removing the effect on success.
Spirit Guardians - Applies an aura effect to the caster, as well as a Sequencer animation. Enemies in the aura will automatically make a saving throw at the start of their turn for a level appropriate amount of damage. Enemies in the aura have their speed halves automatically. Also sets the damage of Spirit Guardians Pulse to the appropriate amount based on the level of the spell that was cast.
Spirit Guardians Pulse - Meant to be manually cast at enemies that enter the aura of Spirit Guardians for the first time on a turn.
Spiritual Weapon - Spawns a token from the actor named "Spiritual Weapon" and places it on the canvas. Grants the token an attack named "Spiritual Weapon Slash" that deals a spell level appropriate amount of damage. Easily customized to spawn a different actor by editing the ItemMacro. Open the Item, click the Item Macro button in the title bar, and change line 2: 'const actorName = "Spiritual Weapon"' Replace "Spiritual Weapon" with the name of the actor you wish to summon. Duplicate the Spiritual Weapon found in the Actors compendium to create an actor that is flagged as invulnerable, and then change the art and name to your liking.
Toll the Dead - Automatically handles which size damage dice to use. By default does d12, but runs a macro when used on a target that checks whether the target is below max health, if it isn't, the damage is programatically changed to use d8s.

##### Items
BoomingBladeItemMacro - Sample weapon that interacts with the Booming Blade spell and the Thrumming Convenient Effect. Either duplicate the item and adjust it to your liking, or copy the ItemMacro over to your own weapon and add a Midi Qol On Use Macro with the settings "ItemMacro" and "Before Damage Roll"
Boots of Elvenkind - Applies a passive effect to the actor granting advantage on stealth skill checks.
Cloak of Displacement - Applies the "Displaced" Convenient Effect to the actor at the start of its turns in combat.
Periapt of Proof Against Poison - Applies a passive effect to the actor granting Immunity to Poison Damage and the Poisoned Condition.
Sentinel Shield +1 - Adds 3 to AC and applies a passive effect to the actor granting Advantage on initiative and Perception skill checks.
Potent Poison - Made by the Poisoner Feat, when used calls for a DC 14 Constitution Save from the target, dealing 2d8 Poison Damage and inflicting the Poisoned Condition on a failure.

#### Signature Items
##### Friday - M&M
###### Angelo
Blooming Rose - Longsword with Finesse. Currently configured with "Sharpened Blade" and "Improved Lethality" - see the entry in the Journal Compendium for details. Plays a different animation when attacking at range.
Petal Slash - Manually rolled to deal 1d4 Magical Slashing damage to a creature after hitting with an attack with Blooming Rose.
Petal Swarm - Reaction ability that rolls 1d4 to determine what to deduct from the triggering attack roll. Set up to not deal any damage so it doesn't matter who/what is targeted.
Guardian Petal Swarm - Ability that rolls 1d6 to determine what to deduct from the triggering attack roll. Set up to not deal any damage so it doesn't matter who/what is targeted. Doesn't use Reaction but instead has Limited Uses that get recharged each turn while Blooming Rose Vortex is active.
Blooming Rose Technique - When used applies an aura effect to the caster. Enemies within the aura have their speed halved and are prompted for a Dexterity Save at the start of their turn, taking 4d8 slashing damage on a fail, half on a success. Also recharges the uses of Guardian Petal Swarm at the start of each of the caster's turns.
Blooming Rose Vortex Slash - Meant to be manually cast at enemies that enter the Blooming Rose Vortext for the first time on a turn.
##### Gavruhnk
[[TODO: Add Aspects and Attunements to the Bracers]]
Greataxe of Barbaric Fury - Currently configured with "Lethality" - see the entry in the Journal Compendium for details.
Bracers of the Totem Warrior - Currently configured with "Runic Etchings" and "Shamanistic Training" - See the entry in the Journal Compendium for details. Shamanistic Training effects need to be manually toggled on/off based on which aspect is chosen to be active after a long rest.
Rage - Applies the benefits of standard rage and also checks to see which totem spirits are active and applies the correct rage specific buffs.
Wolf Spirit Rage - Creates an aura that forces enemies within range to grant advantage on melee attacks against them.
Bear Spirit Rage - Grants resistance to all damage types except psychic and the 3 physical already covered by basic rage.
Elk Spirit Rage - Adds 15 feet to walking movement speed.
Venomfang Spirit Rage - Adds 1d6 + 1/2 Barbarian level Poison Damage to the first successful weapon attack each turn.
##### Taelyx
[[TODO: Create Roll Table for Spirit of Death's Defiance, Create Spirit of Overwhelming Force feature]]
Indensian Battle Plate of the Guardian - Currently Configured as the base item - see the entry in the Journal Compendium for details.
Indensian Warden's Staff - Currently configured with "Aetheric Flow", "Clawed Hand", "Spirit of Potency", "Spirit of Compassion" - See the entry in the Journal Compendium for details. Incorporates the Booming Blade Item Macro.
Spirit of Aggression - Manually rolled to deal damage to the target. Roll Versatile to deal critical damage. Needs to be manually edited to consume the appropriate resource after importing to an actor.
Spirit of Resilience - Manually rolled to use the feature, exists solely to spend the resource with no active effects. Needs to be manually edited to consume the appropriate resource after importing to an actor.
Spirit of Retalitation - Manually rolled to use the feature, exists solely to spend the resource with no active effects. Needs to be manually edited to consume the appropriate resource after importing to an actor.
Spirit of Urgency - Manually rolled to use the feature, exists solely to spend the resource with no active effects. Needs to be manually edited to consume the appropriate resource after importing to an actor.
##### Sapphie
Lilting Performance - When used adds 1 to the number of uses of Bardic Inspiration
Sapphie's Lyre - Currently configured with "Passion" and "Compassionate Song" - see the entry in the Journal Compendium for details.
Sapphie's Battle Dress- Currently configured with "Mithril Weave", "Essence Weaving", and "Focused Mind" - see the entry in the Journal Compendium for details.

#### Monday - M&M
##### Tom
[[TODO: Set up Pocket of Bones to spawn a skeleton via WarpGate, Make Hat of Invisibility feature]]
Tom's Hat - Currently configured with "Essence Weaving" and "Uncommon Glamerweave" - see the entry in the Journal Compendium for details.
Pocket of Holding - standard inventory item with 100 lb weightless capacity.
Pocket of Bones - Currently just a tracker for how many corpses are in the pocket.
Pocket of Life - Adds an effect on the target lasting one hour. Currently just a duration tracket with no mechanical impact.
Mansion in a Hat - Currently just tracks feature usage.
##### Cillian
[[TODO: Create Esoteric Oils, Create Additive Agents, Add throwing animations for bombs, Investigate Active Token Effects for Nighteye Serum]]
Cillian's Prosthetic Arm - Currently configured with "Technique Training" and "Lethality" - see the entry in the Journal Compendium for details.
Javelin Launcher - Currently configured with "Enhanced Fletching" - see the Cillian's Prosthetic Arm entry in the Journal Compendium for details. Item assumes the wielder has a Dexterity score of 10.
Mini Javelin - Standard ammunition item with no mechanical impact.
Rapid Reaction Shield - Manually rolled by the player to indicate their use of the ability and spend their Reaction. No mechanical impact.
Superior Reaction Shield - Manually rolled by the player, rolls 1d8+2 and adds the total as an effect to AC until the start of the caster's next turn. Needs to be manually updated to spend the Superiority Dice resource. The damage expression needs to be manually changed when the character reaches the appropriate levels in Battlemaster Fighter.
Shield Bash - Manually rolled by the player. Prior to the attack roll, a macro rolls a Superiority Die and adds the result to the attack bonus. Needs to be manually updated to spend the Superiority Dice resource. The attack bonus needs to be manually changed when the character reaches the appropriate levels in Battlemaster Fighter.
Witcher Kit - Currently configured with "Aptitude" and set up as a Theoretical Kit with Expertise - see the entry in the Journal Compendium for details.
###### Oils
Lingering Oil - Prompts a save from the target, on a failure applies an effect which deals damage of the designated type at the start of the target's turn for 3 turns. Lingering Oils are meant to be rolled on the target creature after the attack hits.
Impact Oil - Applies a buff to the caster, causing the next successful weapon attack to deal additional damage. Player must activate this item before making the attack roll for it to work properly.
###### Bombs
Glue Bomb - Places a persistent Sequencer effect in targeted area, calls for saves from each creature in area and applies a restrained effect on failure.
Poison Bomb - Calls for saves from each target in the area, deals damage and adds a poisoned effect on a failure, automatically prompts for repeat saves at the end of the target's turn.
###### Serums
Minor Healing Serum - Heals the target for 2d4 hitpoints and applies an effect which heals them for 2d4 at the start of their turn for 3 turns.
Lullaby Serum - Applies an unconscious effect to the target for one hour.
Nighteye Serum - Applies an effect which grants +60 Darkvision to the target.
Steroid Serum - Applies an effect to the target for one hour. No mechanical benefits, purely a duration tracker.
Healing Serum - As Minor Healing Serum, but for 3d8 hitpoints.
Willow Serum - Applies an effect to the target granting immunity to several conditions for 60 seconds.
Wolverine Serum - Applies an effect to the target for one hour. At the start of each of the target's turns, the effect will execute a macro to see if the damage bonus effect needs to be added. Requires importing the GG_WolverineSerum macro from the Macro Compendium and the presence of the "WolverineDamageBonus" Convenient Effect.
##### Bhalgrim
[[TODO: Build Weapon Abilities]]
Diligence, Bulward Against Betrayal - Currently configured with "Runic Etchings", "Vigilant Reminder", "Deflecting Angles", and "Spellguard"(disabled) - see the entry in the Journal Compendium for details.
Reckoning, Legacy of Vengenace - Currently configured with "Runic Etchings", and "Grudge Bearer"(disabled) - see the entry in the Journal Compendium for details.
Restraint (War Hammer) - Currently configured with "Flanged Head" and "Counter-Balance" - see the entry in the Journal Compendium for Reckoning for details.
Restraint (Great Hammer) - Currently configured with "Flanged Head" and "Counter-Balance" - see the entry in the Journal Compendium for Reckoning for details.
Restraint (Pole Hammer) - Currently configured with "Flanged Head" and "Counter-Balance" - see the entry in the Journal Compendium for Reckoning for details.
Fury (War Axe) - Currently configured with "Flanged Head" and "Counter-Balance" - see the entry in the Journal Compendium for Reckoning for details.
Fury (Great Axe) - Currently configured with "Flanged Head" and "Counter-Balance" - see the entry in the Journal Compendium for Reckoning for details.
Fury (Pole Axe) - Currently configured with "Flanged Head" and "Counter-Balance" - see the entry in the Journal Compendium for Reckoning for details
Ardent Shield - Applies an effect to the caster granting the appropriate bonuses to AC and Saves
Ardent Interception - Manually rolled by player to signify use of the ability and spend their reaction. No mechanical benefits.
Raise Shield - Manually rolled by player to signify use of the ability and spend their reaction. No mechanical benefits.
#### Wednesday - M&M
##### Qiana
###### Canister Bombs
See the Canister Bombs Journal Entry for details.
Blaze Burn - Meant to be manually cast at enemies that enter the aura of a burning patch for the first time on a turn.
Blaze Canister - Consumes a Canister Bomb and spawns a Blaze Canister Patch
Poison Canister - Consumes a Canister Bomb and prompts a save from each target in the template area. On a fail deals damage and applies an effect that causes the Poisoned condition and prompts for repeat saves at the end of target's turns.
Shrapnel Canister - Consumes a Canister Bomb and prompts a save from each target in the template area. On a fail deals damage and applies an effect which halves speed until the end of the target's next turn.
###### Ammo
See the Supremacy Ammo Types Journal Entry for details.
+1/+2/+3 Ammo - Applies the bonus to attack and damage rolls with the weapon using the ammo.
Elemental Payload/Infused - Applies a types damage bonus to each shot with the weapon using the ammo.
Pummeling - No mechanical benefit, merely a resource tracker.
Blunderbuss - No mechanical benefit, merely a resource tracker.
###### Items
Survivalit's Pouch - No mechanical benefit
Scavenger's Tools - Individual items keyed to use a specific stat.
Ammo Pouch - simply a container to track which types of ammo are available.
Supremacy - Currently configured with "Enhanced Sights" and "Lethality" - see the entry in the Journal Compendium for details.
Supremacy (Pummeling) - Set to do bludgeoning damage and meant to be used exclusively with Pummeling Ammunition - see the entry in the Journal Compendium for details.
Supremacy (Blunderbuss) - Set to target a cone template instead of 1 creature and meant to be used exclusively with Blunderbuss Ammunition - see the entry in the Journal Compendium for details.
###### Features
Chromatic Infusion - Prompts the user to select a damage type and then applies a buff to the character increasing all weapon damage by 1d6 of the chosen type for one minute.
Targeting Guidance - When cast applies an effect to the caster that increases weapon damage by 1d6 Piercing for one hour.
Reactive Resistance - Manually rolled by player to signify use of the ability and spend their reaction and a use of the feature. No mechanical benefits.
##### Ging
[[TODO: Everything]]
##### Tiko
[[TODO: Create Harnessed Lightning effect/upkeep and Attack, experiment with Directed Power spells, create Violent Resonation ability]]
Artificer's Bladed Tech Staff - Currently configured with "Aetheric Flow", "Serrated Blade", "Mechanized Assistance", "Aetheric Overcharge", and "Specialized Tool" - see the entry in the Journal Compendium for details. The player must manually swap between having Lightning Launcher Bonus Damage and Thunder Gauntlets active.
Aether Trap - Exists purely as a resource usage container, no mechanic impact on its own.
Feed the Trap - Prompts the user for what size of essence they are consuming, then checks the character's inventory for the appropriate item and tries to remove one. If successful, it adds the appropriate amount of charges to the trap item, if it can't find the essence are the quantity of the essence of 0, it displays a prompt to the user to inform them.
Resonating Blade - When used applies an effect to the caster that increases melee damage as well as causing 1 charge to be spent from the trap item at the start of each turn. If there are no charges available to spend, the effect is deleted from the character and a chat message is posted to denote failed upkeep. Manual editing is required to set the ability to consume charges from the trap on the initial use.
##### Haradin
[[TODO: Try and get Concussive Technique Immunity to apply even on a save]]
Nightfall - Currently configured with "Aetheric Flow" and "Puissance" - see the entry in the Journal Compendium for details.
NOTE: All Technique abilities need to be manually edited to consume the correct resource.
Concussive Technique - Prompts the target for a saving throw and applies 2 effects on failure. The immunity effect is purely for tracking with no mechanical interactions.
Deflective Technique - Adds an effect providing an ac bonus to the caster when used.
Focused mind Technique - Manually rolled by player to signify use of the ability and spend their reaction and a use of the feature. No mechanical benefits.
Hemorrhaging Technique - Applies an effect to the target causing them to take damage at the start of each turn for 3 turns.
Path of Twilight Flames Technique - Applies an effect to the caster that last for one minute, Purely a duration tracker and resource consumer, no mechanical impact.
Twilight Hooves - Modified hooves attack to use while Path of Twilight Flames is active.
Twilight Flames Burn - Meant to be manually cast at enemies that enter the aura of a burning patch for the first time on a turn.
##### Dakeal
[[TODO: Elemental Fire Shard]]
#### Tuesday - Humanity's Pride
##### Kivi
[[TODO: Configure Upkeep expenditure on features, audit effect durations]]
###### Items
Fists - Set up to deal 2x Monk's Martial Arts die of the associated damage on a hit.
Kivi's Symbiote - Currently configured with the standard +1 bonus for a base Awakened tier item.
###### Features
NOTE: All Mutation abilities need to be manually edited to consume the correct resource when used.
Awaken Symbiote - Applies an effect to the caster for one hour as a duration tracker. Updates the tertiary character sheet resource to the appropriate amount of Mutation Points.
Heavy Barbs - Applies an effect to the caster increasing ranged weapon damage while active.
I Can Take It - When used rolls the appropriate dice expression to determine how much damage is blocked, no automation to hitpoints.
Launch Barb - Ranged Weapon Attack that consumes charges on the item itself. Charges are generated through other features.
Manifest Barbs - Rolls a die expression and uses the result to set the number of uses on the Launch Barbs abilitiy.
Rapid Growth Barbs - As Manifest Barbs but with different Action Economy and cost.
Rapid Reflexes - Applies an effect to the caster increasing AC and granting advantage on dex saves.
Regeneration - Heals the caster when used.
Snap Out of It - Applies an effect to the caster granting advantage to the next saving throw rolled before the end of the next turn.
Variable Enhancement - No mechanical impact, applies an effect as a duration tracker when used.
##### Ashe
Trinity - Currently configured with the standard +1 bonus for a base Awakened tier item.
Awaken Trinity - Applies an effect to the caster for one hour granting a +10 foot Fly Speed
Giant's Bane - Manually rolled against applicable targets, roll Versatile for crit damage.
Thor's Might - No mechanical impact, exists to track number of uses and communicate intent and feature usage.
Thor's Wrath - Prompts for a saving throw from all targets in the template, dealing 60 Lightning damage on a failure.
##### Hermes
[[TODO: Everything]]
##### Reginalt
[[TODO: Lots]]
Peace Cleric Item - Currently configured with "Empowered Healing", and the standard +1 bonus for a base Awakened tier item.
Awaken Item - Applies an effect to the caster increasing healing done.
Elemental Defensive Matrix - Prompts the user for damage type and applies an effect with resistance to that type until the start of their next turn.
Defensive Matrix - Applies a Shield effect to the caster when used.
Projected Matrix - Applies a Shield effect to the target when used.
Protective Bond - Functions as Misty Step teleport, applies Resistance to all damage for the next instance of damage taken.
Free Bless - Applies a custom bless effect to targets without requiring Concentration.
##### Mento
Lineage - Currently configured with the standard +1 bonus for a base Awakened tier item. Includes the Booming Blade Item Macro.
Legacy - No special mechanics.
Awaken Lineage & Legacy - Applies an effect to the caster for one hour as a duration tracker, rolls the Bladesong item if it exists on the caster.
Flurry - Applies an effect simulating the haste spell to the caster without Concentration.
Generational Fury - Prompts for a saving throw from all selected targets, on a failure deals damage and applies an effect for one turn halving speed.
Sneak Attack - automatically applies sneak attack on the first valid attack each turn. Treats all attacks with Legacy as valid attacks.
