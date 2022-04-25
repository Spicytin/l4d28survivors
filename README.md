Forked from https://forums.alliedmods.net/showpost.php?p=2756041&postcount=220

# Prerequisites

- [Metamod](http://www.sourcemm.net/downloads.php?branch=stable)
- [Sourcemod](https://www.sourcemod.net/downloads.php?branch=stable)

- [L4DToolZ Metamod plugin](https://github.com/Accelerator74/l4dtoolz/releases)
- [Left 4 DHooks Direct](https://forums.alliedmods.net/showthread.php?t=321696)
- [DHooks extension](https://forums.alliedmods.net/showthread.php?p=2588686#post2588686)
- [Stripper:Source](http://www.bailopan.net/stripper/snapshots/1.2/)
    
# Sourcemod Plugins

Configuration files for all the plugins are located in the \cfg\sourcemod directory of your server/game folder.

It is recommended to compile the plugins yourself, especially for older plugins that still work but haven't been updated in years. Just drag all the .sp files in the \addons\sourcemod\scripting folder to the compile.exe file and it will batch compile them into the \scripting\compiled folder.

- [L4D1&2_Signatures](https://github.com/Psykotikism/L4D1-2_Signatures) - If a future update breaks a plugin's gamedata file, get updated signatures here.

- [8+ players Bug Fixes Extension](https://forums.alliedmods.net/showpost.php?p=2721138&postcount=295) - [Linux server files here](https://forums.alliedmods.net/showpost.php?p=2752412&postcount=301)
OR
- [Left-4-fix Collection](https://github.com/LuxLuma/Left-4-fix)
The following plugins from the Left-4-fix collection replace the fixes from the older plugin except for the survivor finale score bug:
 - [Better_Charger_Collision+patch](https://forums.alliedmods.net/showthread.php?t=315482)
 - [Witch fixes](https://forums.alliedmods.net/showthread.php?p=2647014)
The 8+ players bug fixes extension is considered to be a bit outdated but it seems to still work. Left-4-fix collection is newer and has replacements for most of the fixes except for the "finale score bug" fix. According to the 8+ players bug fixes thread it's supposed to fix how many survivors have escaped instead of showing them as deceased. Other bot management plugins may have this type of fix already included so using the newer Left-4-fix plugins might be preferable.

- [Survivor Character Fixes](https://forums.alliedmods.net/showthread.php?p=2771265)
 - Alternative: [Real Zoey Unlock](https://forums.alliedmods.net/showthread.php?t=308483) - (For Windows servers only)
- [Upgrade Pack Fixes](https://forums.alliedmods.net/showpost.php?p=2698228&postcount=5) - fixes upgrade packs being removed when 4 survivors have used them.
- [Defib Fix](https://forums.alliedmods.net/showthread.php?t=315483)
- [Scene Adjustments/Fixes](https://forums.alliedmods.net/showthread.php?t=321127) - fixes friendly fire and mourn quotes for 5+ survivors (seems to stop working on map change for me. If this happens to you, you can add "sm plugins reload sceneadjustments.smx" at the end of your server.cfg to reload the plugin on every map change).
 - [Pre-Update Talker](https://steamcommunity.com/sharedfiles/filedetails/?id=2247536739) - Recommended workshop addon to be used in conjunction with Scene Adjustments plugin. 
The Last Stand update made a number of changes, one of which is that survivors no longer shout the name of the survivor that just died. This talker mod restores the old behavior and works in conjunction with this plugin. Just add the .vpk file to your server's addon folder. You can use the Steam Workshop Downloader to download addons files directly from the Steam Workshop.
- [Save Weapon Co-Op](https://github.com/fbef0102/L4D2-Plugins/tree/master/l4d2_ty_saveweapons) - Saves weapons and health for extra survivors while transitioning to another map. ABM should already be able to do this for all human players, but not for bots. This plugin supports both.
 - Alternative: [Transition Restore Fix](https://forums.alliedmods.net/showthread.php?p=2770962) - Requires [Source Scramble](https://forums.alliedmods.net/showthread.php?t=317175)

- [Character Manager + The Passing Fix](https://forums.alliedmods.net/showthread.php?t=309601) - (download the included stripper files for the passing to prevent players using L4D1 characters from being booted/killed in this campaign)
- [Survivor Chat Select](https://forums.alliedmods.net/showpost.php?p=2738850&postcount=831)
 - Use [Tonblader's config](https://forums.alliedmods.net/showpost.php?p=2727753&postcount=130) for both of these plugins.

- [Left4Fix Extension](https://forums.alliedmods.net/showthread.php?t=219774) - (not to be confused with the Left-4-fix plugin collection) fixes versus score bug for extra survivors, I don't play versus so I haven't tested it.
