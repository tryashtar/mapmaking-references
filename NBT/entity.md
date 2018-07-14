[byte]: https://i.imgur.com/bjqfZyA.png "Byte"
[short]: https://i.imgur.com/io2beuU.png "Short"
[int]: https://i.imgur.com/p9oApza.png "Int"
[long]: https://i.imgur.com/J5syxPr.png "Long"
[float]: https://i.imgur.com/OyOLfNY.png "Float"
[double]: https://i.imgur.com/VtWZquK.png "Double"
[string]: https://i.imgur.com/jD49RLm.png "String"
[compound]: https://i.imgur.com/G66Yglg.png "Compound"
[list]: https://i.imgur.com/nY8RVer.png "List"

### All Entities
---
![string] **`id`**: Entity ID. Changing this with commands will have no effect.  
![list] **`Pos`**: Location of the entity.  
> ![double] X coordinate.  
> ![double] Y coordinate.  
> ![double] Z coordinate.  

![list] **`Motion`**: Velocity of the entity in meters per tick. Each will be reset to `0` if it falls outside `-10 .. 10`.  
> ![double] X component.  
> ![double] Y component.  
> ![double] Z component.  

![list] **`Rotation`**: Rotation of the entity.  
> ![float] Clockwise rotation around Y axis (yaw). If modified, will be moduloed to fall within `0 .. 360`.   
> • `0`: facing south  
> • `90`: facing west  
> • `180`: facing north  
> • `270`: facing east  
>
> ![float] Declination from the horizon around X axis (pitch). If modified, will be moduloed to fall within `-360 .. 360`. Naturally falls within `-90 .. 90`.  
> • `-90`: facing straight up  
> • `0`: facing forward  
> • `90`: facing straight down  

![float] **`FallDistance`**: Distance in meters the entity has fallen. When the entity lands, it takes fall damage equal to `FallDistance - 3` and this resets to `0`.  

![short] **`Fire`**: Ticks remaining while the entity is on fire.  
• `-20`: not on fire (players)  
• `-1`: not on fire (entities)  
• `160`: recently set on fire  
 
![short] **`Air`**: Ticks remaining of breath while the entity is underwater.  
• `0`: drowning  
• `300`: full air  
• `4800`: full air (dolphins)  

![byte] **`OnGround`**: True when the entity is touching the ground.  

![byte] **`NoGravity`**: If true, the entity will not move.  

![int] **`Dimension`**: Current dimension the entity is in.  
• `-1`: in The Nether  
• `0`: in Overworld  
• `1`: in The End  
  
![byte] **`Invulnerable`**: If true, the entity is immune to damage, excluding damage from creative players and the void.  

![int] **`PortalCooldown`**: Ticks remaining until the entity can move through portals.  
• `0`: ready to teleport  
• `300`: recently teleported  

![long] **`UUIDMost`**: Most significant bits of the entity's Universally Unique Identifier. Changing this with commands will have no effect.  

![long] **`UUIDLeast`**: Least significant bits of the entity's Universally Unique Identifier. Changing this with commands will have no effect.  

![string] **`CustomName`**: JSON text component string of the entity's custom name.  

![byte] **`CustomNameVisible`**: If true, the entity's name will appear as a permanent nameplate.  

![byte] **`Silent`**: If true, the entity will not make sounds.  

![list] **`Passengers`**: List of entities that are riding on the entity. Changing this with commands will have no effect.  

![byte] **`Glowing`**: If true, the entity will show a glowing outline.  

![list] **`Tags`**: List of custom strings applied by `/tag`.  
