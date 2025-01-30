# VPK Introduction 

## What is a **[VPK files](https://developer.valvesoftware.com/wiki/VPK_(file_format))**?
VPK (Valve Pak) is a package format used by Valve's **Source Engine** to store game assets such as:

  - Textures
  - Models
  - Sounds
  - Maps
  - Scripts
  - UI elements


VPK files act as uncompressed archives that the game engine can quickly access without needing to extract files beforehand.

## VPK in the Source Engine
In **Source Engine** games (such as Half-Life 2, Team Fortress 2, and Left 4 Dead), VPK files store the majority of the game’s content. The engine loads assets directly from these archives, improving performance and organization.

### **[VPK Files Types](https://developer.valvesoftware.com/wiki/VPK_(file_format))**:
There are two main types of **[VPK files](https://developer.valvesoftware.com/wiki/VPK_(file_format))** in Source-based games:

1. **_dir.vpk** files  
     - These act as an **index** for the game, listing all assets stored in the corresponding data VPKs.  
     - The game engine reads this file first to determine where specific files are located.  
     - Example: `englishclient_mp_common.bsp.pak000_dir.vpk`  

2. **_000.vpk, _001.vpk, etc.**  
     - These contain the actual game data.  
     - The numbering `(_000, _001, etc.)` helps split large files into smaller chunks.  
     - Example: `englishclient_mp_common.bsp.pak000_000.vpk`, `englishclient_mp_common.bsp.pak000_001.vpk`

### How the Game Uses These Files
When the game needs an asset:     

  - It first reads the `_dir.vpk` file to find where the asset is stored.
  - Then, it loads the required asset from the correct numbered VPK file `(_000, _001, etc.)`.
  - This allows for **efficient asset lookup** without loading all files into memory.


## VPK in Titanfall 2  
Titanfall 2, while based on a heavily modified **Source Engine**, also uses **VPK files** to store game content. The difference is:   

  - Titanfall 2 uses a more **advanced version of VPK** compared to older Source games.  
  - The game stores VPK files in the `\Titanfall2\vpks\` directory.  


## Extracting and Modding VPK Files  
Modders often extract and modify **VPK** files to create custom content. The tools to use:  

   - **[Harmony VPK](https://github.com/harmonytf/HarmonyVPKTool)** (recommned to use)  
   - **[Titanfall VPKTool](https://github.com/SenorGeese/Titanfall2/tree/master/tools)** (older tool no longer supported)   

These tools allow users to browse, extract, and repack VPK files.  

### Steps to Extract Titanfall 2 VPK Files  
1. Download **[Harmony VPK](https://github.com/harmonytf/HarmonyVPKTool)**.
2. Locate the VPK files in `Titanfall2/vpks/`.
3. Pick a vpks and use the tool to **extract** the contents. The tools are only able to use `_dir.vpk` files because it tells where the asset is located.
4. Modify assets and repack them if necessary.

### Risks and Considerations

- **Modifying game files can lead to bans** in online play when playing on offical servers.
- Be sure to **backup** your original VPK files before modifying. If you need to restore your vpk do a "Verify Integrity of Games Files" check and it will redownload the correct vpk.