🌎 (your world folder)  
┗ 📁 `datapacks`  
&nbsp; &nbsp; ┗ 🤐 (your data pack)  
&nbsp; &nbsp; &nbsp; &nbsp; ┣ 📝 `pack.mcmeta`  
&nbsp; &nbsp; &nbsp; &nbsp; ┗ 📁 `data`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┗ 📁 (namespaces)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `advancements`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `functions`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `loot_tables`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `recipes`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `structures`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┗ 📁 `tags`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `blocks`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `fluids`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┣ 📁 `items`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ┗ 📁 `functions`  

### `pack.mcmeta`
`pack.mcmeta` is a required file that describes your data pack. It provides a description and a pack version in JSON format, just like a resource pack. Here is an example of the contents:
```json
{
   "pack": {
      "pack_format": 1,
      "description": "My Data Pack"
   }
}
```

### Data
Every piece of data pack data (including vanilla data) is a single file in its corresponding folder, organized using namespaces. The file can be directly in the folder, or it can be inside one or more subfolders.

The namespace folder groups data together. All vanilla data uses the `minecraft` namespace. You can override vanilla files by creating a file in your data pack with the same name in the `minecraft` namespace. If you aren't overriding things, you should create your own namespace to contain your data.

In-game, data files are identified using a "resource location," which consists of the namespace, a colon, then the path to the file without an extension. Some vanilla examples are the `minecraft:bucket` recipe and the `minecraft:chests/simple_dungeon` loot table. Therefore, in the vanilla data pack, these files are located in `data/minecraft/recipes/bucket.json` and `data/minecraft/loot_tables/chests/simple_dungeon.json`.
