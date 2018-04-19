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
> >
> ![float] **`FallDistance`**: Distance in meters the entity has fallen. When the entity lands, the entity takes fall damage equal to `FallDistance - 3` and this resets to `0`.  
> ![short] **`Fire`**: Ticks remaining while the entity is on fire.  
> • `-20`: not on fire (players)  
> • `-1`: not on fire (entities)  
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
> ![byte] **`Invulnerable`**: If true, the entity is immune to damage.  
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
> ![short] **`DeathTime`**: Ticks during which the mob has been playing its death animation.  
> • `.. -80`: no experience will drop  
> • `-80 .. 0`: experience will drop later  
> • `0 .. 19`: experience will drop earlier  
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
> ![byte] **`PersistenceRequired`**: If true, the mob will not naturally despawn.  
> ![byte] **`LeftHanded`**: If true, the mob will hold its main item in its left hand.  
> ![byte] **`Leashed`**: True when the mob is attached to a lead.  
> ![compound] **`Leash`**: The entity or fence coordinate the mob is leashed to. If `Leashed` is false, the connection will be purely visible and will not restrict the mob or break.  
> > ![long] **`UUIDMost`**: Most significant UUID bits of the attached entity.  
> > ![long] **`UUIDLeast`**: Least significant UUID bits of the attached entity.  
> > ![int] **`X`**: X coordinate of the fence.  
> > ![int] **`Y`**: Y coordinate of the fence.  
> > ![int] **`Z`**: Z coordinate of the fence.  

### Breedable Mobs  
> ![int] **`InLove`**: Ticks remaining until the mob stops attempting to breed.  
> • `0`: not trying to breed  
> • `600`: recently fed  
>
> ![int] **`Age`**: When positive, ticks remaining until the mob can breed again. When negative, ticks remaining until the mob becomes an adult.  
> • `-24000`: newborn baby  
> • `0`: adult that can breed  
> • `6000`: adult that just finished breeding  
>
> ![int] **`ForcedAge`**: The value `Age` will be set to when the mob grows up by eating.  
> ![long] **`LoveCauseMost`**: Most significant UUID bits of the player that bred the mob.  
> ![long] **`LoveCauseLeast`**: Least significant UUID bits of the player that bred the mob.  

### Tameable Mobs  
> ![string] **`OwnerUUID`**: Hexadecimal UUID of the player that owns the mob.  
> ![byte] **`Sitting`**: If true, the mob is sitting down.  

### Horses, Donkeys, Mules, Llamas  
> ![byte] **`EatingHaystack`**: True when the mob is grazing.  
> ![byte] **`Tame`**: If true, the mob has been tamed.  
> ![int] **`Temper`**: Ease of taming. Increases when the mob is ridden or fed. Naturally falls within `0 .. 100`.  
> ![string] **`OwnerUUID`**: Hexadecimal UUID of the player that owns the mob.  
> ![compound] **`SaddleItem`**: The saddle item worn by the mob.  

### Donkeys, Mules, LLamas  
> ![byte] **`ChestedHorse`**: If true, the mob is equipped with a chest.  
> ![list] **`Items`**: List of items in the mob's inventory.  

### Zombies, Zombie Villagers, Zombie Pigmen, Husks, Drowned  
> ![byte] **`IsBaby`**: True when the mob is a baby.  
> ![byte] **`CanBreakDoors`**: If true, the mob can break wooden doors.  
> ![byte] **`DrownedConversionTime`**: Ticks remaining until the mob transforms into a drowned.  

### Bat  
> ![byte] **`BatFlags`**: True when the bat is perched upside-down beneath a block.  

### Chicken  
> ![byte] **`IsChickenJockey`**: If true, the chicken will despawn naturally and drop extra experience.  
> ![int] **`EggLayTime`**: Ticks remaining until the chicken lays an egg.  

### Creeper  
> ![byte] **`Powered`**: If true, the creeper is charged with lightning.  
> ![byte] **`ExplosionRadius`**: Size of the creeper's explosion.  
> ![short] **`Fuse`**: The value the internal fuse countdown will be set to when a target enters range.  
> ![byte] **`ignited`**: True when the creeper was ignited with flint and steel.  

### Ender Dragon  
> ![int] **`DragonPhase`**: Current state of the dragon fight (`0` is circling, `1` is shooting a fireball, `2` is moving to the portal, `3` is landing on the portal, `4` is leaving the portal, `5` is shooting dragon breath, `6` is searching for a player, `7` is preparing dragon breath, `8` is charging a player, `9` is moving to the portal to die, `10` is hovering without AI).  

### Enderman  
> ![compound] **`carriedBlockState`**: Block carried by the enderman.  

### Endermite  
> ![int] **`Lifetime`**: Ticks the endermite has existed for.  

### Evoker  
> ![int] **`SpellTicks`**: Ticks remaining until a spell can be cast.  

### Ghast  
> ![int] **`ExplosionPower`**: Size of the fireball's explosion.  

### Horse  
> ![compound] **`ArmorItem`**: The horse armor item worn by the horse.  
> ![int] **`Variant`**  

### Illusioner  
> ![int] **`SpellTicks`**: Ticks remaining until a spell can be cast.  

### Llama  
> ![int] **`Variant`**: Color of the llama (`0` is creamy beige, `1` is white, `2` is brown, `3` is gray).  
> ![int] **`Strength`**: Strength of the llama. Affects inventory size and intimidation of wolves.  
> ![compound] **`DecorItem`**: The carpet item worn by the llama.  

### Magma Cube  
> ![int] **`Size`**: Size of the magma cube.  
> ![byte] **`wasOnGround`**: True when the magma cube is touching the ground.  

### Ocelot  
> ![int] **`CatType`**: Type of the cat (`0` is wild, `1` is tuxedo, `2` is tabby, `3` is siamese).  

### Parrot  
> ![int] **`Variant`**: Color of the parrot (`0` is red, `1` is blue, `2` is green, `3` is cyan, `4` is silver).  

### Phantom  
> ![int] **`Size`**: Size of the phantom.  
> ![int] **`AX`**  
> ![int] **`AY`**  
> ![int] **`AZ`**  

### Pig  
> ![byte] **`Saddle`**: If true, the pig is equipped with a saddle.  

### Rabbit  
> ![int] **`RabbitType`**: Type of the rabbit (`0` is brown, `1` is white, `2` is black, `3` is spotted, `4` is creamy beige, `5` is dark brown, `99` is killer bunny).  

### Sheep  
> ![byte] **`Sheared`**: If true, the sheep is sheared.  
> ![byte] **`Color`**: Color of the sheep's wool (`0` is white, `1` is orange, `2` is magenta, `3` is light blue, `4` is yellow, `5` is lime, `6` is pink, `7` is gray, `8` is light gray, `9` is cyan, `10` is purple, `11` is blue, `12` is brown, `13` is green, `14` is red, `15` is black).  

### Shulker  
> ![byte] **`Peek`**  
> ![byte] **`AttachFace`**: Direction the shulker is facing (`0` is up, `1` is down, `2` is south, `3` is north, `4` is east, `5` is west).  
> ![byte] **`Color`**: Color of the shulker (`0` is white, `1` is orange, `2` is magenta, `3` is light blue, `4` is yellow, `5` is lime, `6` is pink, `7` is gray, `8` is light gray, `9` is cyan, `10` is purple, `11` is blue, `12` is brown, `13` is green, `14` is red, `15` is black, `16` is default).  
> ![int] **`APX`**  
> ![int] **`APY`**  
> ![int] **`APZ`**  

### Skeleton Horse  
> ![byte] **`SkeletonTrap`**: If true, the horse will spawn four horsemen when approached.  
> ![byte] **`SkeletonTrapTime`**: Ticks the trap horse has existed for.  

### Slime  
> ![int] **`Size`**: Size of the slime.  
> ![byte] **`wasOnGround`**: True when the slime is touching the ground.  

### Snow Golem  
> ![byte] **`Pumpkin`**: If true, the snow golem has a pumpkin on its head.  

### Turtle  
> ![int] **`HomePosX`**  
> ![int] **`HomePosY`**  
> ![int] **`HomePosZ`**  
> ![int] **`TravelPosX`**  
> ![int] **`TravelPosY`**  
> ![int] **`TravelPosZ`**  

### Vex  
> ![int] **`BoundX`**: X coordinate of the vex's summon location where it will wander.  
> ![int] **`BoundY`**: Y coordinate of the vex's summon location where it will wander.  
> ![int] **`BoundZ`**: Z coordinate of the vex's summon location where it will wander.  
> ![int] **`LifeTicks`**: Ticks remaining until the vex takes natural damage.  

### Villager  
> ![int] **`Profession`**: Cloak color of the villager (`0` is farmer, `1` is librarian, `2` is cleric, `3` is blacksmith, `4` is butcher, `5` is nitwit).  
> ![int] **`Career`**  
> ![int] **`CareerLevel`**  
> ![byte] **`Willing`**: If true, the villager can breed.  
> ![list] **`Inventory`**: Up to 8 slots of items in the villager's inventory.  
> ![compound] **`Offers`**: Trade offers.  
> > ![list] **`Recipes`**: List of trade options.  
> > > ![compound] A trade option.  
> > > > ![byte] **`rewardExp`**: If true, this trade will produce experience orbs.  
> > > > ![int] **`maxUses`**: Times this trade can be used before locking.  
> > > > ![int] **`uses`**: Times this trade has been used.  
> > > > ![compound] **`buy`**: First item requested.  
> > > > ![compound] **`buyB`**: Second item requested.  
> > > > ![compound] **`sell`**: Item produced by the villager.  

### Iron Golem  
> ![byte] **`PlayerCreated`**: If true, the iron golem will not attack players.  

### Vindicator  
> ![byte] **`Johnny`**: If true, the vindicator will attack all mobs.  

### Wither  
> ![int] **`Invul`**: Ticks remaining until the wither finishes its spawn animation.  

### Wolf  
> ![byte] **`Angry`**: True when the wolf is hostile.  
> ![byte] **`CollarColor`**: Color of the wolf's collar (`0` is white, `1` is orange, `2` is magenta, `3` is light blue, `4` is yellow, `5` is lime, `6` is pink, `7` is gray, `8` is light gray, `9` is cyan, `10` is purple, `11` is blue, `12` is brown, `13` is green, `14` is red, `15` is black).  

### Zombie Pigman  
> ![short] **`Anger`**: Ticks remaining until the zombie pigman becomes neutral.  
> ![string] **`HurtBy`**: Hexadecimal UUID of the player that most recently hurt the zombie pigman.  

### Zombie Villager  
> ![int] **`Profession`**: Cloak color of the zombie villager (`0` is farmer, `1` is librarian, `2` is cleric, `3` is blacksmith, `4` is butcher, `5` is nitwit).  
> ![int] **`ConversionTime`**: Ticks remaining until the zombie villager transforms into a villager.  
> ![long] **`ConversionPlayerMost`**: Most significant UUID bits of the player that cured the zombie villager.  
> ![long] **`ConversionPlayerLeast`**: Least significant UUID bits of the player that cured the zombie villager.  

### Arrow  
> ![int] **`xTile`**: X coordinate of the block the arrow is stuck in.  
> ![int] **`yTile`**: Y coordinate of the block the arrow is stuck in.  
> ![int] **`zTile`**: Z coordinate of the block the arrow is stuck in.  
> ![compound] **`inBlockState`**: Block the arrow is stuck in.  
> ![byte] **`shake`**  
> ![byte] **`pickup`**: Whether the arrow can be picked up (`0` cannot be picked up, `1` can be picked up, `2` can be picked up by creative mode players).  
> ![short] **`life`**: Ticks the arrow has been stuck for.  
> ![double] **`damage`**  
> ![byte] **`inGround`**: True when the arrow is stuck in a block.  
> ![byte] **`crit`**: If true, the arrow travels faster and deals more damage.  
> ![string] **`Potion`**: ID of the potion effect applied by the arrow.  
> ![list] **`CustomPotionEffects`**: List of status effects applied by the arrow.  
> ![int] **`Color`**: RGB color of the arrow's particles.  

### Item  
> ![short] **`Age`**: Ticks the dropped item has existed for. Does not increase when set to `-32768`.  
> ![short] **`Health`**: Health of the dropped item. It dies when this reaches zero.  
> ![short] **`PickupDelay`**: Ticks remaining until the dropped item can be picked up. Does not decrease when set to `32767`.  
> ![compound] **`Thrower`**: The player that dropped the item.  
> > ![long] **`M`**: Most significant UUID bits of the player.  
> > ![long] **`L`**: Least significant UUID bits of the player.  
>
> ![compound] **`Owner`**: The only player that is allowed to pick up the dropped item.  
> > ![long] **`M`**: Most significant UUID bits of the player.  
> > ![long] **`L`**: Least significant UUID bits of the player.  
>
> ![compound] **`Item`**: The item.  

### Experience Orb  
> ![short] **`Age`**: Ticks the orb has existed for. Does not increase when set to `-32768`.  
> ![byte] **`Health`**: Health of the orb. It dies when this reaches zero.  
> ![short] **`Value`**: The number of experience points obtained when the orb is collected.  

### Boat  
> ![string] **`Type`**: Type of the boat (`oak`, `spruce`, `birch`, `jungle`, `acacia,` `dark_oak`).  

### Minecarts  
> ![byte] **`CustomDisplayTile`**: If true, the minecart will display a custom block.  
> ![compound] **`DisplayState`**: Custom block displayed in the minecart.  
> ![int] **`DisplayOffset`**  

### Chest Minecart  
> ![list] **`Items`**: List of items in the chest's inventory.  
> ![string] **`LootTable`**: ID of the loot table used to fill contents.  
> ![long] **`LootTableSeed`**: Seed for generating loot table results.  

### Command Block Minecart  
> ![string] **`Command`**: Command entered in the command block.  
> ![int] **`SuccessCount`**: Result of the previous command's output.  
> ![string] **`LastOutput`**: JSON text component string of the previous command's output.  
> ![byte] **`TrackOutput`**: If true, the command block will store its previous command output.  

### Furnace Minecart  
> ![double] **`PushX`**  
> ![double] **`PushZ`**  
> ![short] **`Fuel`**: Ticks remaining until the furnace fuel is depleted.  

### Hopper Minecart  
> ![list] **`Items`**: List of items in the hopper's inventory.  
> ![string] **`LootTable`**: ID of the loot table used to fill contents.  
> ![long] **`LootTableSeed`**: Seed for generating loot table results.  
> ![int] **`TransferCooldown`**: Ticks remaining until the hopper can transfer an item.  
> ![byte] **`Enabled`**: True when the hopper is not powered and can transfer items.  

### Spawner Minecart  
> ![list] **`SpawnPotentials`**: List of possible entities to spawn.  
> > ![compound] A possible entity.  
> > > ![compound] **`Entity`**: An entity compound.  
> > > ![int] **`Weight`**: Chance this entity will be selected compared to other weights.  
>
> ![compound] **`SpawnData`**: An entity compound of the next entity to be spawned.  
> ![short] **`SpawnCount`**: Number of entities to spawn.  
> ![short] **`SpawnRange`**: Maximum distance in meters entities will be spawned.  
> ![short] **`Delay`**: Ticks remaining until next spawn.  
> ![short] **`MinSpawnDelay`**: Minimum random value for `Delay` after spawning.  
> ![short] **`MaxSpawnDelay`**: Maximum random value for `Delay` after spawning.  
> ![short] **`MaxNearbyEntities`**: Maximum number of similar entities allowed nearby before spawning.  
> ![short] **`RequiredPlayerRange`**: Maximum distance in meters a player must be for spawning.  

### TNT Minecart  
> ![int] **`TNTFuse`**: Ticks remaining until the TNT explodes.  

### Falling Block  
> ![compound] **`BlockState`**: Block that is falling.  
> ![compound] **`TileEntityData`**: Block entity data for the block.  
> ![int] **`Time`**: Ticks the block has existed for.  
> ![byte] **`DropItem`**: If true, the block will produce an item when it breaks.  
> ![byte] **`HurtEntities`**: If true, the block will damage entities it lands on.  
> ![int] **`FallHurtMax`**  
> ![float] **`FallHurtAmount`**  

### TNT  
> ![short] **`Fuse`**: Ticks remaining until the TNT explodes.  

### Area Effect Cloud  
> ![int] **`Age`**: Ticks the cloud has existed for.  
> ![int] **`Color`**: RGB color of the cloud's particles.  
> ![int] **`Duration`**: Maximum `Age` of the cloud before it dies.  
> ![int] **`ReapplicationDelay`**: Ticks in cycle for reapplying effects.  
> ![int] **`WaitTime`**: Minimum `Age` of the cloud before it displays and applies effects.  
> ![int] **`OwnerUUIDMost`**: Most significant UUID bits of the cloud's owner.  
> ![int] **`OwnerUUIDLeast`**: Least significant UUID bits of the cloud's owner.  
> ![float] **`DurationOnUse`**: Increase of `Duration` when an effect is applied.  
> ![float] **`Radius`**: Radius of the cloud in meters.  
> ![float] **`RadiusOnUse`**: Increase of `Radius` when an effect is applied.  
> ![float] **`RadiusPerTick`**: Increase of `Radius` every tick.  
> ![string] **`Particle`**: ID of the particle shown by the cloud.  
> ![string] **`Potion`**: ID of the potion effect applied by the cloud.  
> ![list] **`CustomPotionEffects`**: List of status effects applied by the cloud.  

### Armor Stand  
> ![int] **`DisabledSlots`**  
> ![byte] **`Marker`**: If true, the armor stand will have no hitbox.  
> ![byte] **`Invisible`**: If true, the armor stand will be invisible.  
> ![byte] **`NoBasePlate`**: If true, the armor stand will not display the stone baseplate.  
> ![byte] **`ShowArms`**: If true, the armor stand will display arms.  
> ![byte] **`Small`**: If true, the armor stand will appear smaller.  
> ![compound] **`Pose`**: Rotation for pieces of the armor stand's body.  
> > ![list] **`Body`**: Body rotation.  
> > > ![float] X rotation.  
> > > ![float] Y rotation.  
> > > ![float] Z rotation.  
> >
> > ![list] **`Head`**: Head rotation.  
> > > ![float] X rotation.  
> > > ![float] Y rotation.  
> > > ![float] Z rotation.  
> >
> > ![list] **`LeftArm`**: Left arm rotation.  
> > > ![float] X rotation.  
> > > ![float] Y rotation.  
> > > ![float] Z rotation.  
> >
> > ![list] **`RightArm`**: Right arm rotation.  
> > > ![float] X rotation.  
> > > ![float] Y rotation.  
> > > ![float] Z rotation.  
> >
> > ![list] **`LeftLeg`**: Left leg rotation.  
> > > ![float] X rotation.  
> > > ![float] Y rotation.  
> > > ![float] Z rotation.  
> >
> > ![list] **`RightLeg`**: Right leg rotation.  
> > > ![float] X rotation.  
> > > ![float] Y rotation.  
> > > ![float] Z rotation.  

### Ender Crystal  
> ![byte] **`ShowBottom`**: If true, the bedrock bottom will display.  
> ![compound] **`BeamTarget`**: The block targeted by the beam.  
> > ![int] **`X`**: X coordinate of the block.  
> > ![int] **`Y`**: Y coordinate of the block.  
> > ![int] **`Z`**: Z coordinate of the block.  

### Evocation Fangs  
> ![int] **`Warmup`**: Ticks remaining until the fangs appear.  
> ![int] **`OwnerUUIDMost`**: Most significant UUID bits of the fangs' owner.  
> ![int] **`OwnerUUIDLeast`**: Least significant UUID bits of the fangs' owner.  

### Fireworks Rocket  
> ![int] **`Life`**: Ticks the rocket has existed for.  
> ![int] **`LifeTime`**: Maximum `Life` of the rocket before it explodes.  
> ![compound] **`FireworksItem`**: Fireworks rocket item.  
  
