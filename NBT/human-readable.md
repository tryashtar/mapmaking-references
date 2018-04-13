### Entity  
> `id`: Entity ID.  
> `Pos`: Location of the entity.  
> > X coordinate.  
> > Y coordinate.  
> > Z coordinate.  
>  
> `Motion`: Velocity of the entity in meters per tick.  
> > X component.  
> > Y component.  
> > Z component.  
>  
> `Rotation`: Rotation of the entity.  
> > Clockwise rotation around Y axis (yaw).  
> > Declination from the horizon around X axis (pitch).  
>  
> `FallDistance`: Distance in meters the entity has fallen. Determines fall damage.  
> `Fire`: Remaining ticks while the entity is on fire.  
> `Air`: Remaining ticks of breath while the entity is underwater.  
> `OnGround`: True when the entity is touching the ground.  
> `NoGravity`: If true, the entity will not move.  
> `Dimension`: Current dimension of the entity (`0` for Overworld, `-1` for Nether, `1` for End)  
> `Invulnerable`: If true, the entity is immune to damage.  
> `PortalCooldown`: Remaining ticks until the entity can move through portals.  
> `UUIDMost`: Most significant bits of the entity's Universally Unique Identifier.  
> `UUIDLeast`: Least significant bits of the entity's Universally Unique Identifier.  
> `CustomName`: A JSON text component string of the entity's custom name.  
> `CustomNameVisible`: If true, the entity's name will appear as a permanent nameplate.  
> `Silent`: If true, the entity will not make sounds.  
> `Passengers`: List of entity compounds that are riding on this entity.  
> `Glowing`: If true, the entity will show a glowing outline.  
> `Tags`: List of custom strings.  
  
### Mob/Player  
> `Health`: Amount of health the mob has, in half-hearts.  
> `AbsorptionAmount`  
> `HurtTime`: Remaining ticks until the mob finishes its hurt animation.  
> `DeathTime`: Ticks during which the mob has been dead.  
> `FallFlying`: True when the mob is flying with elytra.  
> `Attributes`: List of attributes for this mob.  
> > An attribute.  
> > > `Name`: The attribute ID.  
> > > `Base`: The default value.  
> > > `Modifiers`: List of active modifiers.  
>  
> `ActiveEffects`: List of active potion effects.  
>  
> `HandItems`: Items in the mob's hands.  
> > Item in the mob's main hand.  
> > Item in the mob's off hand.  
>  
> `ArmorItems`: Items in the mob's armor slots.  
> > Item in the mob's feet slot.  
> > Item in the mob's legs slot.  
> > Item in the mob's chest slot.  
> > Item in the mob's head slot.  
>  
> `HandDropChances`: Chances that hand items will drop on death.  
> > Chance that the main hand item will drop.  
> > Chance that the off hand item will drop.  
>  
> `ArmorDropChances`: Chances that armor items will drop on death.  
> > Chance that the feet slot item will drop on death.  
> > Chance that the legs slot item will drop on death.  
> > Chance that the chest slot item will drop on death.  
> > Chance that the head slot item will drop on death.  
>  
> `DeathLootTable`: ID of loot table used for mob drops on death.  
> `DeathLootTableSeed`: Seed for generating loot table results.  
> `CanPickUpLoot`: If true, the mob can equip weapons and armor from the ground.  
> `NoAI`: If true, the mob will not move or make any AI actions.  
> `PersistenceRequired`: If true, the mob will not naturally despawn.  
> `LeftHanded`: If true, the mob will hold its main item in its left hand.  
> `Leashed`: True when the mob is attached to a lead.  
> `Leash`: The entity or fence coordinate the mob is leashed to.  
> > `UUIDMost`: Most significant UUID bits of the attached entity.  
> > `UUIDLeast`: Least significant UUID bits of the attached entity.  
> > `X`: X coordinate of the fence.  
> > `Y`: Y coordinate of the fence.  
> > `Z`: Z coordinate of the fence.
