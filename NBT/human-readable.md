[byte]: https://i.imgur.com/cXHccQS.png "Byte"
[short]: https://i.imgur.com/rireehT.png "Short"
[int]: https://i.imgur.com/02KlQEx.png "Int"
[long]: https://i.imgur.com/UJwhcS1.png "Long"
[float]: https://i.imgur.com/iUxlS14.png "Float"
[double]: https://i.imgur.com/ohTfAW4.png "Double"
[string]: https://i.imgur.com/fm3DXhX.png "String"
[list]: https://i.imgur.com/oRRFndw.png "List"
[compound]: https://i.imgur.com/NeqiPhl.png "Compound"

### Entity  
> ![string] `id`: Entity ID.  
> ![list] `Pos`: Location of the entity.  
> > ![double] X coordinate.  
> > ![double] Y coordinate.  
> > ![double] Z coordinate.  
>  
> ![list] `Motion`: Velocity of the entity in meters per tick.  
> > ![double] X component.  
> > ![double] Y component.  
> > ![double] Z component.  
>  
> ![list] `Rotation`: Rotation of the entity.  
> > ![float] Clockwise rotation around Y axis (yaw).  
> > ![float] Declination from the horizon around X axis (pitch).  
>  
> ![float] `FallDistance`: Distance in meters the entity has fallen. Determines fall damage.  
> ![short] `Fire`: Remaining ticks while the entity is on fire.  
> ![short] `Air`: Remaining ticks of breath while the entity is underwater.  
> ![byte] `OnGround`: True when the entity is touching the ground.  
> ![byte] `NoGravity`: If true, the entity will not move.  
> ![int] `Dimension`: Current dimension of the entity (`0` for Overworld, `-1` for Nether, `1` for End)  
> ![byte] `Invulnerable`: If true, the entity is immune to damage.  
> ![int] `PortalCooldown`: Remaining ticks until the entity can move through portals.  
> ![long] `UUIDMost`: Most significant bits of the entity's Universally Unique Identifier.  
> ![long] `UUIDLeast`: Least significant bits of the entity's Universally Unique Identifier.  
> ![string] `CustomName`: A JSON text component string of the entity's custom name.  
> ![byte] `CustomNameVisible`: If true, the entity's name will appear as a permanent nameplate.  
> ![byte] `Silent`: If true, the entity will not make sounds.  
> ![list] `Passengers`: List of entity compounds that are riding on this entity.  
> ![byte] `Glowing`: If true, the entity will show a glowing outline.  
> ![list] `Tags`: List of custom strings.  
  
### Mob/Player  
> ![float] `Health`: Amount of health the mob has, in half-hearts.  
> ![float] `AbsorptionAmount`  
> ![short] `HurtTime`: Remaining ticks until the mob finishes its hurt animation.  
> ![short] `DeathTime`: Ticks during which the mob has been dead.  
> ![byte] `FallFlying`: True when the mob is flying with elytra.  
> ![list] `Attributes`: List of attributes for this mob.  
> > ![compound] An attribute.  
> > > ![string] `Name`: The attribute ID.  
> > > ![double] `Base`: The default value.  
> > > ![list] `Modifiers`: List of active modifiers.  
>  
> ![list] `ActiveEffects`: List of active potion effects.  
>  
> ![list] `HandItems`: Items in the mob's hands.  
> > ![compound] Item in the mob's main hand.  
> > ![compound] Item in the mob's off hand.  
>  
> ![list] `ArmorItems`: Items in the mob's armor slots.  
> > ![compound] Item in the mob's feet slot.  
> > ![compound] Item in the mob's legs slot.  
> > ![compound] Item in the mob's chest slot.  
> > ![compound] Item in the mob's head slot.  
>  
> ![list] `HandDropChances`: Chances that hand items will drop on death.  
> > ![float] Chance that the main hand item will drop.  
> > ![float] Chance that the off hand item will drop.  
>  
> ![list] `ArmorDropChances`: Chances that armor items will drop on death.  
> > ![float] Chance that the feet slot item will drop on death.  
> > ![float] Chance that the legs slot item will drop on death.  
> > ![float] Chance that the chest slot item will drop on death.  
> > ![float] Chance that the head slot item will drop on death.  
>  
> ![string] `DeathLootTable`: ID of loot table used for mob drops on death.  
> ![long] `DeathLootTableSeed`: Seed for generating loot table results.  
> ![byte] `CanPickUpLoot`: If true, the mob can equip weapons and armor from the ground.  
> ![byte] `NoAI`: If true, the mob will not move or make any AI actions.  
> ![byte] `PersistenceRequired`: If true, the mob will not naturally despawn.  
> ![byte] `LeftHanded`: If true, the mob will hold its main item in its left hand.  
> ![byte] `Leashed`: True when the mob is attached to a lead.  
> ![compound] `Leash`: The entity or fence coordinate the mob is leashed to.  
> > ![long] `UUIDMost`: Most significant UUID bits of the attached entity.  
> > ![long] `UUIDLeast`: Least significant UUID bits of the attached entity.  
> > ![int] `X`: X coordinate of the fence.  
> > ![int] `Y`: Y coordinate of the fence.  
> > ![int] `Z`: Z coordinate of the fence.
