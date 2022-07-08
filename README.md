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
- [8 Player Modified Talker](https://steamcommunity.com/sharedfiles/filedetails/?id=2462741269) - Self-explainatory.

OR
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

# SI Limit & Spawn Management

Incase if controlling special infected limit and spawn rates in ABM & SuperVersus didn't work for you, you can try adding one of these plugins. They may won't conflict with ABM / SuperVersus / Infected Bots Control:

- [Balancer Spawn Infected](https://forums.alliedmods.net/showthread.php?p=2694407) - Balances SIs limit and spawn interval depending on the number of players.
- [ZSpawn](https://forums.alliedmods.net/showthread.php?t=332272) - Modify director spawns. Also you can spawn special infecteds manually without affecting human players in versus. NEEDS SETTING zspawn_autotank_scav_score IN l4d2_zspawn.cfg TO 0 INSTEAD OF 10 TO AVOID SPAWNING SEVERAL TANKS IN SCAVENGE FINALES! Don't know why this was default.

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

# Dedicated Server

It's recommended to use a dedicated server for plugins, a local host/listenserver can exhibit weird bugs and crashes. Normally it's recommended to use SteamCMD however there is a simpler way.

With Steam open, make sure that you have the option to show all tools and uninstalled items. 

Look for Left 4 Dead 2 Dedicated Server and install it. It'll be an extra 9GB give or take. While you can hit play and start your dedicated server this way, it is not recommended since it will exhibit some weird bugs, such as not detecting steamids of players and showing them all as 0:0. Steam will also show you as "playing" the dedicated server, even if you are playing L4D2. This means they can't easily join your lobby or game from the main menu and will have to connect directly. You would also have to setup Sourcemod with username and password authentication since steamid will be borked, which is not recommended. While starting it this way does let you start and stop the game and server at will, it causes too many weird issues.

For simple LAN server to play with friends, create a batch file, such as "runserver.bat" in the \common\Left 4 Dead 2 Dedicated Server folder, with the following code:

> start "" srcds -usercon -console -insecure -dev -game left4dead2 -port 27000 +hostname "Game Server" +map c8m1_apartment +maxplayers 8 +sv_lan 1  

We don't really need the extra -debug and -condebug options but you can add them if you wish. To play with people over the internet, change sv_lan to 0 and forward the port in your router. The values in your server.cfg will override what's here. I personally prefer to remove "-console" to get an old-school looking interface to launch your server. It is limited in that it won't allow you to select all maps, however that doesn't matter because the server will load whatever you pick from the lobby anyway. The main reason I choose the gui is because it has autocomplete when typing in commands and values.

You can then create a shortcut to the batch file and place it on your desktop. To play on the same machine as the dedicated server, you can launch the batch file before starting Steam. If you do that, you can start and exit L4D2 as many times as you want as long as the server is still running. If Steam is already running, you have to launch L4D2 first, and then the server. When done this way, if you exit L4D2, Steam will show that you are already "playing" L4D2 and will not let you launch it. The only way to get back in without closing your dedicated server is to launch the L4D2 game executable directly. You will get a message box saying that you are running it with the -insecure option since that is how we have the server launched. You can ignore it since we are not playing on Valve servers.

To run commands inside your game, you will need to add your steamid to the \addons\sourcemod\configs\admins_simple.ini file. You can use a steamid finder online or copy your steamid from abm log file if using that plugin. To give yourself admin privileges, just add:

> "steamid"    "z"  
  
to the file. Replace the "steamid" with your steamid. To change variables from within the game and run some commands, you will need to add:
    
> rcon_password "PASSWORD"
    
to both the server.cfg of your dedicated server and the autoexec.cfg in your game folder (create it if it doesn't exist). Most plugin commands should just run as is without needing rcon, such as ABM commands. I recommend binding your most commmonly used commands to keys. 
   
You can load and unload sourcemod plugins without restarting your server. If you add new plugins or move some to the disabled folder you can use "sm plugins refresh" and sourcemod will unload plugins that are no longer there and load any new plugins. If you are replacing a plugin with the same name you will have to use "sm plugins load nameofplugin.smx" or the number listed using "sm plugins list".

# To have an 8 player lobby:

- [8 slots lobby fixed](https://steamcommunity.com/sharedfiles/filedetails/?id=2754956355)

OR
- [8 Player Lobby](https://steamcommunity.com/sharedfiles/filedetails/?id=2276071285) - Requires you to choose it from custom mutation list and then change game type to your desired one.

In your client's autoexec.cfg file, make sure to add your server's ip and port numbers, whether you're playing on the same computer as the dedicated server or if on another computer.

> mm_dedicated_force_servers "ip:port"  

If you don't, you will have to run this command every time you start the game.
Then just pick "Best Available Dedicated Server" when creating your lobby. If your are running a listen/local server, just pick the "Local Server" option and make sure you started the game with the -insecure launch option.

If playing a LAN game, all players on the network will see your name in the lower left hand corner of the main menu screen where they can then join your lobby. Should also work for people on your friends list over the internet. Just remember to forward the port in your router. If players over the internet have issues joining the game when you start it from the lobby, they can just connect directly using "connect ip:port".

If loading screen gets stuck, just press ESC key ones and the map will finish loading. It doesn't happen when loading a campaign for the first time, but it does happen when advancing to the next map, at least for me.
