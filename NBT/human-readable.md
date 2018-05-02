
[byte]: https://i.imgur.com/bjqfZyA.png "Byte"
[short]: https://i.imgur.com/io2beuU.png "Short"
[int]: https://i.imgur.com/p9oApza.png "Int"
[long]: https://i.imgur.com/J5syxPr.png "Long"
[float]: https://i.imgur.com/OyOLfNY.png "Float"
[double]: https://i.imgur.com/VtWZquK.png "Double"
[string]: https://i.imgur.com/jD49RLm.png "String"
[compound]: https://i.imgur.com/G66Yglg.png "Compound"
[list]: https://i.imgur.com/nY8RVer.png "List"

---

![byte] **Byte**: `-128 .. 127`, ends with `b`.  
![short] **Short**: `-32768 .. 32767`, ends with `s`.  
![int] **Int**: `-2147483648 .. 2147483647`.  
![long] **Long**: `-9223372036854775808 .. 9223372036854775807`, ends with `L`.  
![float] **Float**: Any real number, ends with `f`.  
![double] **Double**: Any real number, ends with `d`.  
![string] **String**: Text wrapped in quotes.  
![compound] **Compound**: Named values between curly brackets.  
![list] **List**: Unnamed values of the same type between square brackets.  

---

### Entity  
> ![string] **`id`**: Entity ID. Changing this with commands will have no effect.  
> ![list] **`Pos`**: Location of the entity.  
> > ![double] X coordinate.  
> > ![double] Y coordinate.  
> > ![double] Z coordinate.  
>
> ![list] **`Motion`**: Velocity of the entity in meters per tick. Each will be reset to `0` if it falls outside `-10 .. 10`.  
> > ![double] X component.  
> > ![double] Y component.  
> > ![double] Z component.  
>
> ![list] **`Rotation`**: Rotation of the entity.  
> > ![float] Clockwise rotation around Y axis (yaw). If modified, will be moduloed to fall within `0 .. 360`.   
> > • `0`: facing south  
> > • `90`: facing west  
> > • `180`: facing north  
> > • `270`: facing east  
> >
> > ![float] Declination from the horizon around X axis (pitch). If modified, will be moduloed to fall within `-360 .. 360`. Naturally falls within `-90 .. 90`.  
> > • `-90`: facing straight up  
> > • `0`: facing forward  
> > • `90`: facing straight down  
>
> ![float] **`FallDistance`**: Distance in meters the entity has fallen. When the entity lands, it takes fall damage equal to `FallDistance - 3` and this resets to `0`.  
> ![short] **`Fire`**: Ticks remaining while the entity is on fire.  
> • `-20`: not on fire (players)  
> • `-1`: not on fire (entities)  
> • `160`: recently set on fire  
> 
> ![short] **`Air`**: Ticks remaining of breath while the entity is underwater.  
> • `0`: drowning  
> • `300`: full air  
> • `4800`: full air (dolphins)  
>
> ![byte] **`OnGround`**: True when the entity is touching the ground.  
> ![byte] **`NoGravity`**: If true, the entity will not move.  
> ![int] **`Dimension`**: Current dimension of the entity.  
> • `-1`: in The Nether  
> • `0`: in Overworld  
> • `1`: in The End  
>  
> ![byte] **`Invulnerable`**: If true, the entity is immune to damage, excluding creative players and void damage.  
> ![int] **`PortalCooldown`**: Ticks remaining until the entity can move through portals.  
> • `0`: ready to teleport  
> • `300`: recently teleported  
>
> ![long] **`UUIDMost`**: Most significant bits of the entity's Universally Unique Identifier. Changing this with commands will have no effect.  
> ![long] **`UUIDLeast`**: Least significant bits of the entity's Universally Unique Identifier. Changing this with commands will have no effect.  
> ![string] **`CustomName`**: JSON text component string of the entity's custom name.  
> ![byte] **`CustomNameVisible`**: If true, the entity's name will appear as a permanent nameplate.  
> ![byte] **`Silent`**: If true, the entity will not make sounds.  
> ![list] **`Passengers`**: List of entities that are riding on the entity Changing this with commands will have no effect.  
> ![byte] **`Glowing`**: If true, the entity will show a glowing outline.  
> ![list] **`Tags`**: List of custom strings applied by `/tag`.  

### Mob/Player  
> ![float] **`Health`**: Amount of health the mob has, in half-hearts. Cannot exceed the mob's `generic.maxHealth` attribute.  
> ![float] **`AbsorptionAmount`**: Amount of yellow absorption health the mob has, in half-hearts. Damage is applied to this health first.  
> ![short] **`HurtTime`**: Ticks remaining until the mob finishes its hurt animation.  
> • `10`: recently hurt  
> • `0`: not recently hurt  
>
> ![short] **`DeathTime`**: Ticks during which the mob has been playing its death animation.  
> • `.. -80`: after dying, no experience will drop  
> • `-80 .. 0`: after dying, experience will drop later than usual  
> • `0 .. 19`: after dying, experience will drop earlier than usual  
> • `20 ..`: after dying, the mob will be permanently invisible, uninteractable, and stuck in the world
>
> ![byte] **`FallFlying`**: True when the mob is flying with elytra.  
> ![list] **`Attributes`**: List of attributes for this mob.  
> > ![compound] An attribute.  
> > > ![string] **`Name`**: The attribute ID.  
> > > ![double] **`Base`**: The default value.  
> > > ![list] **`Modifiers`**: List of active modifiers.  
>
> ![list] **`ActiveEffects`**: List of active status effects.  
>
> ![list] **`HandItems`**: Items in the mob's hands. Empty slots exist as empty compounds.  
> > ![compound] Item in the mob's main hand.  
> > ![compound] Item in the mob's off hand.  
>
> ![list] **`ArmorItems`**: Items in the mob's armor slots. Empty slots exist as empty compounds.  
> > ![compound] Item in the mob's feet slot.  
> > ![compound] Item in the mob's legs slot.  
> > ![compound] Item in the mob's chest slot.  
> > ![compound] Item in the mob's head slot.  
>
> ![list] **`HandDropChances`**: Proportion chances that armor items will drop on death. Each defaults to `0.085` and is set to `2.0` when an item is picked up. When greater than `1.0`, durability will not be randomized.  
> > ![float] Chance that the main hand item will drop.  
> > ![float] Chance that the off hand item will drop.  
>
> ![list] **`ArmorDropChances`**: Proportion chances that armor items will drop on death. Each defaults to `0.085` and is set to `2.0` when an item is picked up. When greater than `1.0`, durability will not be randomized.   
> > ![float] Chance that the feet slot item will drop on death.  
> > ![float] Chance that the legs slot item will drop on death.  
> > ![float] Chance that the chest slot item will drop on death.  
> > ![float] Chance that the head slot item will drop on death.  
>
> ![string] **`DeathLootTable`**: ID of the custom loot table used for mob drops on death.  
> ![long] **`DeathLootTableSeed`**: Seed for generating custom loot table results.  
> ![byte] **`CanPickUpLoot`**: If true, the mob can equip weapons and armor from the ground when the `mobGriefing` gamerule is true.  
> ![byte] **`NoAI`**: If true, the mob will not move or make any AI actions.  
> ![byte] **`PersistenceRequired`**: If true, the mob will not naturally despawn. Set to true when a mob equips an item or is renamed with a name tag.  
> ![byte] **`LeftHanded`**: If true, the mob will hold its main item in its left hand.  
> ![byte] **`Leashed`**: True when the mob is attached to a lead.  
> ![compound] **`Leash`**: The entity or fence coordinate the mob is leashed to. If `Leashed` is false, the connection will be purely visible and will not restrict the mob or break.  
> > ![long] **`UUIDMost`**: Most significant UUID bits of the attached entity.  
> > ![long] **`UUIDLeast`**: Least significant UUID bits of the attached entity.  
> > ![int] **`X`**: X coordinate of the fence.  
> > ![int] **`Y`**: Y coordinate of the fence.  
> > ![int] **`Z`**: Z coordinate of the fence.  
