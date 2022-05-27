Based from https://forums.alliedmods.net/showpost.php?p=2756041&postcount=220

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
- [Defib Fix](https://forums.alliedmods.net/showthread.php?t=315483) - fixes defib getting wrong targets and reviving alive players.

The 8+ players bug fixes extension is considered to be a bit outdated but it seems to still work. Left-4-fix collection is newer and has replacements for most of the fixes except for the "finale score bug" fix. According to the 8+ players bug fixes thread it's supposed to fix how many survivors have escaped instead of showing them as deceased. Other bot management plugins may have this type of fix already included so using the newer Left-4-fix plugins might be preferable.

- [Survivor Character Fixes](https://forums.alliedmods.net/showthread.php?p=2771265)
  - Alternative: [Real Zoey Unlock](https://forums.alliedmods.net/showthread.php?t=308483) - (For Windows servers only)
- [Upgrade Pack Fixes](https://forums.alliedmods.net/showpost.php?p=2698228&postcount=5) - fixes upgrade packs being removed when 4 survivors have used them.
- [Dialogue Criteria Fix](https://forums.alliedmods.net/showthread.php?t=335875) - Not recommended with 4 survivor servers and no character changing plugins.
- [Scene Adjustments/Fixes](https://forums.alliedmods.net/showthread.php?t=321127) - fixes friendly fire and mourn quotes for 5+ survivors (seems to stop working on map change for me. If this happens to you, you can add "sm plugins reload sceneadjustments.smx" at the end of your server.cfg to reload the plugin on every map change).
  - [Pre-Update Talker](https://steamcommunity.com/sharedfiles/filedetails/?id=2247536739) - Recommended workshop addon to be used in conjunction with Scene Adjustments plugin. The Last Stand update made a number of changes, one of which is that survivors no longer shout the name of the survivor that just died. This talker mod restores the old behavior and works in conjunction with this plugin. Just add the .vpk file to your server's addon folder. You can use the Steam Workshop Downloader to download addons files directly from the Steam Workshop.
- [Save Weapon Co-Op](https://github.com/fbef0102/L4D2-Plugins/tree/master/l4d2_ty_saveweapons) - Saves weapons and health for extra survivors while transitioning to another map. ABM should already be able to do this for all human players, but not for bots. This plugin supports both.
  - Alternative: [Transition Restore Fix](https://forums.alliedmods.net/showthread.php?p=2770962) - Requires [Source Scramble](https://forums.alliedmods.net/showthread.php?t=317175)

- [Character Manager + The Passing Fix](https://forums.alliedmods.net/showthread.php?t=309601) - (download the included stripper files for the passing to prevent players using L4D1 characters from being booted/killed in this campaign)
- [Survivor Chat Select](https://forums.alliedmods.net/showpost.php?p=2738850&postcount=831)
  - Use [Tonblader's config](https://forums.alliedmods.net/showpost.php?p=2727753&postcount=130) for both of these plugins.

- [Left4Fix Extension](https://forums.alliedmods.net/showthread.php?t=219774) - (not to be confused with the Left-4-fix plugin collection) fixes versus score bug for extra survivors, I don't play versus so I haven't tested it.

Pick one of these music plugins below (you can also combine both):
- [Dynamic Soundtrack Sets](https://forums.alliedmods.net/showpost.php?p=2732709&postcount=26) - Plays appropriate music for L4D1 and 2 survivors.
- [L4D1 Music Fix](https://github.com/LuxLuma/L4DMusic_stuff) - fixes few L4D2 musics (Left 4 Death for example) being played in L4D1 maps instead of L4D1 ones.

# Player/Bot management & Difficulty Scaling

There are 3 main choices for bot management and difficulty scaling:

- [ABM](https://forums.alliedmods.net/showpost.php?p=2748953&postcount=517) - [(config guide)](https://gitlab.com/vbgunz/ABM)

ABM is an all in one tool, however since it has not been updated in a while, some features don't work, for example the identity fix, the automodel feature and the model chooser menu, necessitating the use of survivor chat select plugin. It only lets you change a model for the survivor of the current map (either LD1 or LD2) but not both, even if enabled by other plugins. The settings for autodifficulty are also not as granular as other plugins. It's very good for server management, such as having teleport and respawn menus, and the ability to create and remove bots at will.

If you only want the plugin to create new survivors when a new player joins, set
> abm_minplayers "4" 

in the abm.cfg file. If you just want to have all 8 survivors spawn as bots from the beginning and just have new players take over a bot when they join, set it to
> abm_minplayers "8" 

or however may survivors you want to start with, up to the amount set in sv_maxplayers in your server.cfg or listenserver.cfg file. ABM will also let you start with less than 4 survivors, if you want to just play with just 2 or 3 survivors instead of 4.

If you want to let this plugin control the difficulty scaling, I recommend you lower the extra health given to a tank to make it more proportional to the extra number of players, such as setting it to:
> abm_tankchunkhp "1000" 

Across the different difficulties, this insures that the tank health is at 200% when you have 8 survivors.

- [SuperVersus](https://forums.alliedmods.net/showpost.php?p=2722171&postcount=1311) - [(Updated gamedata file)](https://forums.alliedmods.net/showpost.php?p=2724932&postcount=1322)

The plugin has been kept alive over the years but has older code compared to newer plugins. See [here](https://forums.alliedmods.net/showpost.php?p=2746267&postcount=1352) for more info.
MaxSpecials amount may not be scaled correctly, just use
"sm plugins reload l4d_superversus_latest.smx" (or whatever the name of your plugin file happens to be) after starting your server. See [here](https://forums.alliedmods.net/showpost.php?p=2756037&postcount=1369).

Survivor management may not be as polished and may exhibit weird bugs such as requiring restart on Helm's Deep map, bots not being properly added or pruned, players being thrown to spectators team etc., but difficulty scaling is great.

If you only want the plugin to create new survivors when a new player joins, set
>l4d_static_minimum_survivor "4"

and
>l4d_survivor_limit "8" 

in the l4d_superversus.cfg file. If you just want to have all 8 survivors spawn as bots from the beginning and just have new players take over a bot when they join, set it to
>l4d_static_minimum_survivor "8"

and
>l4d_survivor_limit "8" 

or however may survivors you want to start with. For more than 8 players set l4d_survivor_limit to match your sv_maxplayers value.

- [Multislots](https://forums.alliedmods.net/showpost.php?p=2715546&postcount=249)
- [CreateSurvivorBot](https://forums.alliedmods.net/showpost.php?p=2729883&postcount=16)
- [Infected Bots Control](https://forums.alliedmods.net/showpost.php?p=2699220&postcount=1369)

Multislots is stricly for player/bot management, so it's usually paired with infected bots control plugin for difficulty scaling. CreateSurvivorBot plugin is needed for Multislots.
Do keep in mind that out of all the management plugins, Mulstislots and Infected Bots Control are the only ones so far that are still regularly receiving updates and bug fixes at this point in time. If this is important to you this combo is recommended.

If you only want the plugin to create new survivors when a new player joins, set
>l4d_multislots_max_survivors "4"

and
>l4d_multislots_spawn_survivors_roundstart "0" 

in the l4dmultislots.cfg file. If you just want to have all 8 survivors spawn as bots from the beginning and just have new players take over a bot when they join, set it to
>l4d_multislots_max_survivors "8"

and
>l4d_multislots_spawn_survivors_roundstart "1" 

or however may survivors you want to start with. For more than 8 players set l4d_multislots_max_survivors to match your sv_maxplayers value.

# Other Combinations

You can also use different combinations of player management and difficulty scaling plugins. 

1:

- [ABM](https://forums.alliedmods.net/showpost.php?p=2748953&postcount=517)
- [SuperVersus with No Player Management](https://forums.alliedmods.net/showpost.php?p=2750000&postcount=1356)

When using ABM with another plugin that handles the zombie difficulty scaling, you must disable the difficulty scaling options in ABM's config. Mainly these:
>abm_autohard "0" 

and
>abm_tankchunkhp "0"  

2:

- [ABM](https://forums.alliedmods.net/showpost.php?p=2748953&postcount=517)
- [Infected Bots Control](https://forums.alliedmods.net/showpost.php?p=2699220&postcount=1369)

3:

- [Multislots](https://forums.alliedmods.net/showpost.php?p=2715546&postcount=249)
- [CreateSurvivorBot](https://forums.alliedmods.net/showpost.php?p=2729883&postcount=16)
- [SuperVersus with No Player Management](https://forums.alliedmods.net/showpost.php?p=2750000&postcount=1356)

# Useful Extra Plugins

Pick one of those campaign switcher plugins below:
- [Improved Automatic Campaign Switcher](https://forums.alliedmods.net/showthread.php?t=308708) - Change to any campaign automatically after finale by voting. Requires MissionManager and its AdminMenu.
- [CampaignShift](https://forums.alliedmods.net/showpost.php?p=2756038&postcount=36) - Change to campaign chronologically after end of the game credits or by vote to skip.
  - [Transition Info Fix](https://forums.alliedmods.net/showthread.php?p=2762953) - Useful with one of the plugins above.

- [Gear Transfer](https://forums.alliedmods.net/showthread.php?t=137616) - Allows transferring items such as molotovs, pipe bombs, defibs, etc. to teammates.
- [Black & White Notifier](https://forums.alliedmods.net/showthread.php?p=2612147) - Notifies players when a survivor is in black and white status and will make them glow.
- [Incapped Crawling with Animation](https://forums.alliedmods.net/showthread.php?t=137381) - Enables survivor crawling and adds the crawling animation to incapped players.
- [Drop Secondary Improved](https://forums.alliedmods.net/showpost.php?p=2720089&postcount=26) (Plugin) or [Legacy Weapon Manager](https://steamcommunity.com/sharedfiles/filedetails/?id=2608563050) (Addon) - Makes survivors drop their secondary weapons in addition to their primary ones when dying.
- [Respawn Rescue Closet](https://forums.alliedmods.net/showthread.php?t=223138) - You can also just use ABM's respawn menu although they will respawn with full heath. Either way, unfortunately respawn closets in the game can only respawn up to 3 survivors, creating closets with this plugin is a possible solution. Not sure if there is a way to make the game spawn more than 3.
- [No Friendly-fire](https://forums.alliedmods.net/showthread.php?p=2559951) - This plugin blocks damage which also blocks survivor responses. Alternatively, just add these lines to your server.cfg/listenserver.cfg file. Survivors will still respond to friendly fire.

> sm_cvar survivor_friendly_fire_factor_normal "0"    //default 0.1

> sm_cvar survivor_friendly_fire_factor_hard "0"        //default 0.3 

> sm_cvar survivor_friendly_fire_factor_expert "0"    //default 0.5  
