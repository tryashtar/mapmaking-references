[byte]: https://i.imgur.com/bjqfZyA.png "Byte"
[short]: https://i.imgur.com/io2beuU.png "Short"
[int]: https://i.imgur.com/p9oApza.png "Int"
[long]: https://i.imgur.com/J5syxPr.png "Long"
[float]: https://i.imgur.com/OyOLfNY.png "Float"
[double]: https://i.imgur.com/VtWZquK.png "Double"
[string]: https://i.imgur.com/jD49RLm.png "String"
[compound]: https://i.imgur.com/G66Yglg.png "Compound"
[list]: https://i.imgur.com/nY8RVer.png "List"

### All Mobs  
[**(All Entities)**](entity.md)

---
![float] **`Health`**: Amount of health the mob has, in half-hearts. Cannot exceed the mob's `generic.maxHealth` attribute.  

![float] **`AbsorptionAmount`**: Amount of yellow absorption health the mob has, in half-hearts. Damage is applied to this health first.  

![short] **`HurtTime`**: Ticks remaining until the mob finishes its hurt animation.  
• `10`: recently hurt  
• `0`: not recently hurt  

![short] **`DeathTime`**: Ticks during which the mob has been playing its death animation.  
• `.. -80`: after dying, no experience will drop  
• `-80 .. 0`: after dying, experience will drop later than usual  
• `0 .. 19`: after dying, experience will drop earlier than usual  
• `20 ..`: after dying, the mob will be permanently invisible, uninteractable, and stuck in the world

![byte] **`FallFlying`**: True when the mob is flying with elytra.  

![list] **`Attributes`**: List of attributes for this mob.  
> ![compound] An attribute.  
> > ![string] **`Name`**: The attribute ID.  
> > ![double] **`Base`**: The default value.  
> > ![list] **`Modifiers`**: List of active modifiers.  

![list] **`ActiveEffects`**: List of active status effects.  

![list] **`HandItems`**: Items in the mob's hands. Empty slots exist as empty compounds.  
> ![compound] Item in the mob's main hand.  
> ![compound] Item in the mob's off hand.  

![list] **`ArmorItems`**: Items in the mob's armor slots. Empty slots exist as empty compounds.  
> ![compound] Item in the mob's feet slot.  
> ![compound] Item in the mob's legs slot.  
> ![compound] Item in the mob's chest slot.  
> ![compound] Item in the mob's head slot.  

![list] **`HandDropChances`**: Proportion chances that armor items will drop on death. Each defaults to `0.085` and is set to `2.0` when an item is picked up. When greater than `1.0`, durability will not be randomized.  
> ![float] Chance that the main hand item will drop.  
> ![float] Chance that the off hand item will drop.  

![list] **`ArmorDropChances`**: Proportion chances that armor items will drop on death. Each defaults to `0.085` and is set to `2.0` when an item is picked up. When greater than `1.0`, durability will not be randomized.   
> ![float] Chance that the feet slot item will drop on death.  
> ![float] Chance that the legs slot item will drop on death.  
> ![float] Chance that the chest slot item will drop on death.  
> ![float] Chance that the head slot item will drop on death.  

![string] **`DeathLootTable`**: ID of the custom loot table used for mob drops on death.  

![long] **`DeathLootTableSeed`**: Seed for generating custom loot table results.  

![byte] **`CanPickUpLoot`**: If true, the mob can equip weapons and armor from the ground when the `mobGriefing` gamerule is true.  

![byte] **`NoAI`**: If true, the mob will not move or make any AI actions.  

![byte] **`PersistenceRequired`**: If true, the mob will not naturally despawn. Set to true when a mob equips an item or is renamed with a name tag.  

![byte] **`LeftHanded`**: If true, the mob will hold its main item in its left hand.  

![byte] **`Leashed`**: True when the mob is attached to a lead.  

![compound] **`Leash`**: The entity or fence coordinate the mob is leashed to. If `Leashed` is false, the connection will be purely visible and will not restrict the mob or break.  
> ![long] **`UUIDMost`**: Most significant UUID bits of the attached entity.  
> ![long] **`UUIDLeast`**: Least significant UUID bits of the attached entity.  
> ![int] **`X`**: X coordinate of the fence.  
> ![int] **`Y`**: Y coordinate of the fence.  
> ![int] **`Z`**: Z coordinate of the fence.  
