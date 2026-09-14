# Command tierlist

## Quick ruleset

This article is for ranking most of the commands in Minecraft on a tierlist. This tier list is aimed at Java Edition 26.3. These commands will be ranked primarily on how useful the are to command block and datapack development, but secondarily how convenient they are for people who *don't* do commands or datapacks. 

Commands with a permission level greater than 2, multiplayer only commands, most speaking commands (`/me`,`/msg`, etc.) and aliases are omitted. The commands that will be ranked are:
- `/advancement`
- `/attribute`
- `/bossbar`
- `/clear`
- `/clone`
- `/compute`
- `/damage`
- `/data`
- `/datapack`
- `/defaultgamemode`
- `/dialog`
- `/difficulty`
- `/effect`
- `/enchant`
- `/execute`
- `/fetchprofile`
- `/fill`
- `/fillbiome`
- `/forceload`
- `/function`
- `/gamemode`
- `/gamerule`
- `/give`
- `/item`
- `/kill`
- `/list`
- `/locate`
- `/loot`
- `/particle`
- `/place`
- `/playsound`
- `/posteffect`
- `/random`
- `/recipe`
- `/reload`
- `/return`
- `/ride`
- `/rotate`
- `/say`
- `/schedule`
- `/scoreboard`
- `/seed`
- `/setblock`
- `/setworldspawn`
- `/spawnpoint`
- `/spectate`
- `/spreadplayers`
- `/stopsound`
- `/stopwatch`
- `/summon`
- `/swing`
- `/tag`
- `/team`
- `/tellraw`
- `/test`
- `/tick`
- `/time`
- `/title`
- `/tp`
- `/trigger`
- `/waypoint`
- `/weather`
- `/worldborder`
- `/xp`
 
`/experience` is an alias of `/xp`, so it's omitted; and `/teleport` is an alias of `/tp`, so it's omitted as well.

Now for how the tiers will be sorted out:

**S tier**: used *everywhere*; absolute game-changer across the board.  
**A tier**: very useful, but not used all the time and/or has some quirk that makes it less useful.  
**B tier**: quite solid when needed. It could also fill an important role, but do so with a couple caveats.  
**C tier**: You won't be using these too often; commands that serve a niche purpose well.  
**D tier**: There's either a much better way to achieve this goal OR is quite flawed; however not *entirely* useless.

The tiers will be further separated using + or -, to determine if they are strong or weak (e.g. A- is still A tier, but closer to B tier, A tier is in the middle, and A+ is nearing S tier.)

Now, onto the tierlist:

## The tier list

### 1. `/advancement`

This command is useful for two main reasons:
1. You can use it to give advancements; primarily useful for testing, or for advancement packs if you plan on having an unconventional requirement not detectable by one trigger (e.g. *BACAP*)
2. Taking away advancements. This is the most common use for `/advancement`, as advancements are mostly used for various forms of detection in datapacks.

Strong start so far, but it cannot be put in to S-tier for 2 reasons:
1. Advancements aren't always useful, and
2. More importantly, everything outside of granting/revoking **one** advancement isn't very useful, so `/advancement (grant|revoke) <targets> (everything|from|through|until)` aren't useful all that much.

Still a very strong command, so it'll be put into **A tier**.

### 2. `/attribute`

Another very strong command, `/attribute` is used to deal with attributes and attribute modifiers on living entities. With this command you are able to:
- set the base value of an entity's attribute;
- get the current value of an entity's attribute (including modifiers); and
- manipulate an entity's attributes via modifiers.

This command is not useful because of the one thing it controls, but the **multitude** of things it controls; Attributes control things like attack speed, attack range, jump strength, movement speed, gravity, hitbox scale, and many, many, more things. 

The only flaw with this command isn't the command itself, but how attribute modifiers on players **reset on death**. On top of that, you only use the command when manipulating these attributes. For these reasons, `/attribute` gets a very strong **A+**.

### 3. `/bossbar`

The `/bossbar` command is interesting, since it concerns bossbars. An example is the bossbar you see when fighting the Ender Dragon or Wither.

Bossbars created by the command have a namespaced ID (e.g. `example:foo`), and can be customized in many ways, including its
- color (albeit only 7 available colors)
- players it's visible for
- maximum value
- current value (via the command or by `/execute store`)
- segment style (whether it's divided into either 6, 10, 12 or 20 segments, or unsegmented - the default)
- visible name (as a text component), and
- whether its visible to any of the players it's visible for.

There is, however one glaring problem: bossbars aren't used that often. They can be used for primarily two things:
- As a way to display numerical information (e.g. a boss' health), or
- As a way to display a message at the top of the screen, this is not as common however.

Another thing is that there are only *seven* colors to choose from, and only 5 segmentation options, these are less important to the ranking.

Over all, `/bossbar` serves one somewhat niche purpose quite well; therefore, it gets a **B tier**.

### 4. `/clear`

Back to the useful commands, `/clear` removes items from a players inventory. You are able to specify what item, what components the item should have (via a component predicate, used also in `/execute if items`) and the maximum amount to remove. If the max count is `0`, it **queries** the amount of items without removing any, useful for obtaining the amount of items in a player's inventory.

Overall, it serves a very clear and easy purpose, and additionally, is very easy to use for **anyone**; just type `/clear`, and your inventory is cleared. However, there is a couple of things that are important to cover:
1. This isn't the only way to modify items, In 26.3, `/item` got a revamp, allowing for very fine inventory manipulation not only for players, but for other mobs like villagers, and block entities like chests.
2. It can't remove an item off of a specific slot, `/item` can.

Regardless, I will put this in to **A-**, simply because it's more convenient than using `/item` for everything, for non command users and command users alike.

### 5. `/clone`

This is an interesting command, since `/clone` allows you to duplicate or move a specfic area; these areas can even be in separate dimensions. On top of that, you get options whether to only paste non-air (so keeping all other blocks in the pasting reigon) *or* only copy certain blocks using a filter. Despite `/clone` being very useful for copying areas, there are 3 caveats:

1. The syntax is quite annoying; specifically the destination field requires you to know the bottom northwest corner of the region.
2. This command is **very** resource intensive for bigger regions
3. Weirdly enough, for most of the time, you don't work with blocks in a way that you *need* it, since you have to either create a reigon with commands (which is annoying at best), or hardcode one.

This command is also quite unfriendly to the casual player, and is quite unintuitive to work with; however when it's needed, a *lot* can be done with it. For these reasons, I'll give it a **B**

### 6. `/compute`

You might not recognize this command, since it was added in 26.3. Basically, it allows you to compute context integer and float providers, and you are given three context types, which are useful for predicate resolving. These context providers got **incredibly** useful in 26.3, allowing you to do arithmetic with decimals, on top of exponents, square root, sine, and cosine.

There is just one flaw with this command, however: It can't really *store* decimals. This is because the command is best used via the `/execute store result` subcommand, which **only returns integers**; if you return a float, it just gets truncated. Because of this, the `/data` command was changed to be able to set a value based off of this command's syntax.

This command isn't useless however, as you can still use decimals, the decimal just gets cut off for the return value; it is still the fastest way to compute context number providers and store them in scoreboards or bossbars. Because of these reasons, and `/data` filling the void of decimal storage, I'll put this command in **B tier**. Though one might actually include the `/data` change with it, since it uses the same syntax as this command. If you count that, `/compute` would be in the **S tier**.

Overall, **B tier**.

### 7. `/damage`

The `/damage` command is not the only way to damage entities with commands, but it is by **far** the best option. With the `/damage` command, you can specify exactly how much damage you want to apply, what damage type, and supply context to those damage types, like who did it and where did it happen.

I don't have much to say, because this command does everything quite well; however, I think `/damage` should support negative health, because there isn't a way to heal a player that isn't hacky, or that isn't awkward. On top of this, you aren't damaging entities all the time, but I'd say it isn't as niche as `/bossbar`.

For these reasons, I'll put `/damage` in **A-**, since it serves it's purpose quite well, and there isn't an alternative good enough.

### 8. `/data`

This is, in my opinion, the second most powerful command in Minecraft, and that's simply because it allows for the access and manipulation of NBT, in all forms. Most entity data, like Position, Rotation, and many other things are controlled by the entity's NBT. Block entities have NBT that's used to store data, like items in a chest. Most importantly, is *command storage* - a separate container for NBT whose very *purpose* is for command users and datapackers.

NBT allows for the storage of *many* datatypes, like integers, decimals, bytes, strings, arrays and other JSON-like objects. `/scoreboard` allows you to store integers, but not everything `/data` can. You are also given a *lot* of control over how to set an NBT value; from another NBT location, a substring of a valid string in an NBT location, and as mentioned earlier, context number providers. Here, decimals **fully work**.

There is so much that `/data` covers that I can't go over without spending so much time on it. The one flaw with this command is *performance*. I'd say that `/data` takes up the **most** amount of lag in a datapack when used. This command is also not too useful for casual command users. However, this doesn't change my ranking as NBT as a whole is so powerful, and this command is the only gateway to that world. For these reasons, `/data` gets a very solid **S tier**, but not **S+**.

### 9. `/datapack`

The `/datapack` command allows for the control of loading and unloading datapacks, directly through a datapack!

It's not uncommon for datapacks nowadays to have dependencies, addon datapacks, or potentially incompatibilities that have to be managed. `/datapack` therefore, allows a datapack to disable certain datapacks, or enable them at a different priority (This changes things like entity tags if `"replace": false`).

You are also able to get the enabled and available (so they're in the world file, but aren't enabled) datapacks, which is accessible for datapacks by running `/datapack list [available|enabled]` inside a command block, and from there, the output is accessible through `/data`.

This can also be useful for casual commanders that are using, say a datapack in a world, but wants to disable it. `/datapack create`, added recently, allows operators to generate a datapack folder with `pack.mcmeta` already generated. Outside of these three purposes, `/datapack` isn't very useful. 

Overall, the `/datapack` command is quite useful for manipulating datapacks within a datapack. However, there should be a better way for datapacks to check the existence of a datapack within a world, and also it's still quite niche. Therefore, `/datapack` goes into **B tier**.

### 10. `/defaultgamemode`

This command is the simplest so far, and basically sets the gamemode players get put into when they join the world for the first time in a server. If in a LAN world, or in a server with `force-gamemode` enabled, all online players are forced into the default gamemode set by this command. Not very useful outside of this, but it's still usable in a datapack. I'll put this command in **D+**, since I can't find a good reason to force **all** online players into a gamemode through a datapack, and the setting is essentially configurable in a server's `server.properties`.

### 11. `/dialog`

Back to the good commands, `/dialog` either shows a dialog to a player, or closes the one they're in. This dialog can either be inline or specified in a datapack, which makes it viable for non-datapack use. 

Dialogs themselves are interesting, since they are basically custom UI elements, that are still meant to look like Minecraft, so they aren't customizable. You can still make buttons that do run commands, and even send server packets I believe.

Dialogs themselves though can be quite niche however, and there's a warning for running most commands, so string input doesn't work.

I could go on about dialogs themselves, but this is ranking the *commnand*. Overall, `/dialog` is quite good, allowing a datapack or command block to show or hide dialogs from players, and that dialog doesn't have to be in a file. Dialogs themselves though aren't used too much outside of UI. For those reasons, `/dialog` gets a strong **B+**, close to **A-**, but not quite.

### 12. `/difficulty`

Being even simpler than `/defaultgamemode`, this command just changes the world difficulty, or query the current difficulty by running just `/difficulty`. On servers, the difficulty gets set to the one in `server.properties` on restart, so it's good for temporary difficulty changes.

That being said, it's more useful than `/defaultgamemode`, since `/difficulty peaceful` is a quick way to remove monsters, but outside of convenience sake, it doesn't serve a good purpose. I will put this command in **C**, since it's server quirks, and `/difficulty peaceful` can be used.

### 13. `/effect`

This command allows you to add or remove potion effects from living entities. You can specify:
- what effect
- duration in seconds (or `infinite`)
- amplifier (how strong the effect is)
- whether to hide particles and HUD display

You are also able to remove effects using `/effect clear <targets> [<effect>]`. If `[<effect>]` is omitted, then it clears *all* entity effects.

This command doesn't have that much wrong - it's always nice to give players saturation, or night vision. They do reset on death, but it's super easy to just regive them. I do wish that time was in ticks instead of seconds.

For these reasons, `/effect` goes into **A**. There's most likely an effect that will be used, and being able to hide particles, and supply infinite time is very nice.

### 14. `/enchant`

This command enchants the item in your mainhand with the specified enchantment with the specified level. The enchantment **cannot** be illegal in the sense that
- The item has to be compatible with the enchantment (e.g. you cannot apply protection to a tool);
- If the enchantment results in 2 mutually exclusive enchantments being put on the same item (e.g. trying to put mending on a bow with infinity), the command fails; and
- The enchantment level **cannot** exceed that of the enchantment's `max_level` field (e.g. you cannot apply sharpness 6 onto a sword with this enchantment)
 
It also only works on players.

As a datapacker, I don't really find a use for this command outside of testing the legality of custom enchantments - if it's legal, it'll show up here; this is because the restrictions can be bypassed using item modifiers. 

For a casual player though (like I was at some point), it's very convenient because you don't need to grab an anvil with all your books to enchant an item. For these reasons, as well as the level restriction, I will put this command into **C+**.

### 15. `/execute` (the GOAT)

This is **by far** the best command in Minecraft, and there is no second place. If you don't know what I mean, `/execute` can
- run ANY command as multiple entities - including commands only compatible with one target (e.g. `/data get entity`)
- run a command at the position of ANY entity
- run a command at any position, rotation OR dimension in general
- use conditional statements using the many `/execute [if|unless]` subcommands
- store the result or successfulness of a command to a scoreboard, bossbar or NBT location
- and on top of this, run any command right after.

These might not sound too ridiculous on paper (if you live under a rock), but combined? That's where it gets **FAR** beyond the scope of this tierlist. `/execute` is so good, that even if it did not get revamped in 1.13, it would still place near the *top* of the list (like #2 or 3, but still in S tier).

This command obviously gets an **S+**.

### 16. `/fetchprofile`

Ok, calming down now, `/fetchprofile` allows you to fetch the profile of another Minecraft user, by either their name, UUID or via a target selector if they're online. When fetching by name or UUID, the request will go to Microsoft's servers, and if the profile is resolved, you will be able to:
- copy the `profile` component of that request,
- give yourself a player head with the component, or
- summon a mannequin using that profile component.

Since the components resolve into a Base64 encoded texture, even if the player's skin changes, that profile will point to the same texture generated when `/fetchprofile` was run. This is very useful for getting certain player heads or mannequin skins inside a map. However, the main problem is use within datapacks.

Using `/fetchprofile id <UUID>` or `/fetchprofile name <name>` in a function or command block will *always* succeed, regardless of actual failure. You cannot use conventional command block output, because even on success, the message allowing you to summon mannequins, copy components or give heads doesn't show up. Using `/fetchprofile entity <target>` does work, although there is a better alternative. This completely disallows accessing the actual date within Minecraft *accurately and cosistently*, which - even though not always useful - would've been super cool.

However, due to the things already discussed, I wil put the command into **C+**, because while entirely useless for datapack development, it's actually quite nice of a tool for mapmakers and casual players (in the command sense).

### 17. `/fill`

A classic. Basically, you describe the region you want to fill out with 2 sets of coordinates, you specify which block you want, and that's the gist of it. There are some other interesting features with `/fill`, like:
- only replaceing specific blocks using a filter;
- only replacing non-air blocks;
- destroying blocks as if with a tool (unenchanted diamond pickaxe in this case, since that by default can access every non-silk touch drop);
- placing without applying initial block updates (useful for water, sand, etc.); and
- creating an outline, which either hollows out the center or keeps it. Keep in mind that this only works if the length of all axes (X, Y, and Z) are at least 3.

Overall, this command is very usefull for filling out a rectangle or cuboid shape out of blocks, and the only flaw I can think of is that you should be able to specify the tool or loot method for `destroy`. I'll give this an **A tier**, but close to A+.

### 18. `/fillbiome`

This was definitely one of the most requested commands for Minecraft, and it was added in 1.16. Basically, you describe a region like in `/fill`, and specify the biome. You can also choose to only replace specific biomes with a filter.

> [!NOTE]
>
> You might find that the biomes aren't acutally in the area you wanted - likely larger or smaller in certain regions. This is becuase Minecraft stores biomes in 4x4 regions instead, and those regions are also blended into irregular shpaes.

Overall, a niche command, but serves its purpose well. The only limitation is not within the command itself, but how Minecraft sets them, as stated in the note above

I will give this command a **B+**, because while not as useful as `/fill`, it's a very nice feature when you need it.

### 19. `/forceload`

This is a particularly great command, as it marks specified chunks for entity ticking (the highest level for loaded chunks). This is really useful, say, when you need an entity in a certain place to be loaded at all times. You can also unmark chunks for forceloading. This command especially became useful when spawn chunks were removed in 1.21.9. Additionally, you can query for if a position is forceloaded, or query all forceloaded chunks.

While this command isn't used everywhere, keeping a loaded area is necessary for commands that modify blocks, target selectors, etc. For these reasons, I will put this at **A+**, nearing an **S-**, because no other command inside of Minecraft can force an area to be loaded (you can summon an ender pearl to keep an area loaded, but that's not permanent).

### 20. `/function`

The `/function` command is simple: it runs a function or function tag, with optional macro values that can be passed in. Command functions are essentially the heart of datapacks, since they can run multiple commands instantly, and they remember **context** (what ran, and where it ran). On top of this, being able to supply macro values to pass in is likely the best thing Mojang has added since the `/execute` revamp.

While yes, non datapackers basically have no use for this, it's so useful for datapacks that it earns the bronze medal for best command (only behind `/data` and `/execute`), and that's because datapacks *technically* aren't necessary to build most things that don't require macros. For these reasons, `/function` will be given an **S tier**.

### 21. `/gamemode`

Now for some simple commands, `/gamemode` allows you to change a player's gamemode through commands. With 1.16 adding the F3+F4 gamemode switcher, `/gamemode` for convenience sake is quite irrelevant now. Changing the player's gamemode - especially from and to spectator - is quite useful for certain minigames.

I will put this command into **B-**, since it does it's job (unsuprisingly), but it doesn't have too many use cases.

### 22. `/gamerule`

The `/gamerule` command allows you to change game rules via commands. Since 26.1, it has become slightly less relevant for casual players, since the *World Options* menu was added, but is quite useful for datapack setup. For example, a datapack might need to set the `max_block_modifications` gamerule to a high number for dealing with large `/fill` or `/clone` regions, or set `keep_inventory` or `limited_crafting` to true. It's a form of setup, and that's still useful. 

Another great example is enabling and disable PvP using the `pvp` gamerule, and enabling it after a set time.

For these reasons, `/gamerule` will be put into **A-**.

### 23. `/give`

Another great command, `/give` allows you to give a player any item, while allowing you to set the item's components, and also in any amount, up to 100 stacks of that item.

This command is very simple, and is very intuitive, you pick it up like how any normal item would; this is one advantage that `/give` has over its competitor `/item`.

I really don't have much else to say, this command is just **great**, and anyone can use it. For these reasons, `/give` joins the the greats with an **S-**. It cannot be ranked higher because it's quite simplistic in nature, and there are more advanced ways of dealing with items.

### 24. `/item`

Speaking of items, next is the `/item` command. In 26.3, this command got a substantial revamp allowing for the modification of multiple slots (via `/item fill` and `/item override`, as well as the `/item [replace|modify]` changes), and allowing for the use of **slot sources**, which can select slots by their contents and other things.

Additionally, you are able to apply item modifiers on these slots, being able to modify *any* component (except for some that are unusable like `creative_slot_lock`).

With `/item`, you aren't limited to player's inventories either; you can modify any entity's inventory and any block entity with an inventory the same way.

This command is so great because you have *full control* over inventories, especially after 26.3. For these reasons, `/item` goes in the **S tier**, but not stronger than `/function`, `/data` or `/execute`

### 25. `/kill`

This is one of the simplest commands so far, and it basically just kills entities. This is already *very* useful, since you get to remove any unwanted entities using a target selector (just want to be careful though).

Due to it's simplistic nature, there isn't much to talk about. However, this doesn't change the rating: I will give it **A+**, very close to S-. It's a very good cleanup method for entities like markers, and is usable by anyone due to its simplicity.

### 26. `/list`

The `/list` command lists all players online in a server, with an extra option to list there UUIDs as well. I only put it here because:

1. It's usable in singleplayer, and
2. There are potential use cases for it

For example, it is one way to get a player's name. It's also the only way of to directly get the player's UUID in hyphenated hexadecimal form, which can be used in commands (there are tools to turn UUID arrays into hexadecimal form, but it isn't direct). It's also a way of getting the amount of online players in a server, via `/execute store`.

These use cases are, at best, very rare, except for getting online players. It's also a bit unintuitive, since you have a list of hexadecimal UUIDs, but you have to find a weird way to assign them.

Overall, there is possible use cases, but they are small at best, and there are better ways. I'll give it a **C-**.

### 27. `/locate`

The `/locate` command allows the player to locate the nearest structure, biome or point of interest, and teleport to it. The command will fail if nothing is found within a around 12.8k blocks (256 for point of interests), and provide a clickable `/tp` command to the location.

This command, to be honest, isn't useful for datapacks, but sure is very useful for custom structures, and finding structures in-game - especially with the speed improvement in 26.3.

There is a potential usecase because the coordinates and `/tp` command are accessible via a command block's output, which could maybe be used in some datapack where you are to be teleported to the nearest structure. However, you aren't given the Y axis, and it sends you to the `0 0` chunk coordinate of the starting portion of a structure.

Overall, there likely isn't a good purpose within command blocks, but for general use, it works well. I'll give it a **B-**, due to its potential (if configured properly).

### 28. `/loot`

Back to actually useful commands, `/loot` invokes a loot table, and can spawn the items in multiple ways, like:
- giving them to a player;
- inserting them into a block inventory (e.g. a chest);
  - you can also choose to replace slots inside a container or entity; and
- by spawning them in directly as item entities.

From there you can choose to give the loot in multiple ways, where you can simulate fishing, killing a mob, or mining a specific block, or invoke a loot table directly; this loot table can be inline, allowing for the use of macros.

When you want to give a player items based off of a loot table, this is the way to do it. The other options (except for fishing simulations) are useful in their own, niche way, as they supply basically all of the required loot context for each simulation.

While not being as universal as `/give` or `/item`, being able to give out loot tables on demand is quite useful. For that reason, `/loot` will go inside of the **A tier**, close to an A+.

### 29. `/particle`

This is one of the most complex commands to place in the tierlist, despite it's simple purpose: create particles. These particles can have have configuration options with braces (e.g. `foo{config:<example>}`), and can be configured with amount, speed, a delta variable (these two are *weird* when creating more than one particle), whether it's forced (so people you have *Minimal* particles in their settings), and who can even see them to begin with.

This command is hard to place, because it heavily depends on what you're working on. This command is *great* for creating subtle details inside of builds, and can be used to make interesting shapes or animations because of how particles work.

The main problem with `/particle` however, is usability. To make one of these cool animations requires using hundreds of `/particle` commands; maybe not directly, but using the `/execute` command to change orientation or whatever to place more precisely. This makes building things with particle effects very unfun without tools (e.g. online generators).

The `/particle` command has potential to place quite strongly, but it's
1. Not useful for technical development, as particles are client sided and cannot be detected or anything like that; in other words, they're purely visual.
2. Very hard to use for beginners, except for some particles (e.g. `explosion_emitter`).
3. Very unintuitive if you want to make something beyond, say a splash. (very silly and overexaggerative example, but it suffices here)

For these reasons, `/particle` gets put into **B+**, but can be placed anywhere from B to A, depending on who you ask. It's quite powerful, but implementation and usability doesn't cut it.

### 30. `/place`

This is an interesting command, since it allows you to *place* any structure, feature or template, as long as it meets certain requirements (these can be quite strict however, for example, end cities are hard to place). A good use case for this command, is to place really large structures using the `/place jigsaw` command. Jigsaw structures can be up to 257x257 blocks in each axis.

Using `/place feature` could also be good for placing features like trees, amethyst geodes and monster rooms in precise locations. It is also quite good for testing custom structures, jigsaws, features without having to implement them into the world first.

Overall, the main purpose is quite niche, but being able to place large structures is the best part. For these reasons, `/place` will be placed in **B tier**.

### 31. `/playsound`

This is a cool command, since it allows you to play a sound event at a specific place and for specfic players. You get a lot customization of the sound itself, like
- the pitch of the sound (effectively within 0.5 and 2.0)
- the volume (hearing radius once > 1)
- the players who can hear it
- the sound channel that it plays on (i.e what category of sound is it; e.g. sounds in the `master` channel are controlled by the master volume slider in the sound settings)
- the minimum volume for players outside of the range set by `volume`

This basically covers every possible configuration, minus the fact that sound *events* can cover a group of sounds (e.g. there's multiple zombie groaning sound effects, but under only one sound event) instead of a specific sound location.

Overall, `/playsound` serves its purpose very well, and is very configurable, and I don't have anything against the command. Therefore, this command goes into **A-**. This command is actually quite well made, but it's more of an afterthought, like most commands based on atmosphere, like `/particle`.

### 32. `/posteffect`

This is the other command added in 26.3, and is also *very* powerful, but again, on the atmospheric (technically beyond that) side of things. The `/posteffect` command allows for the manipulation of post effects on a client; post effects are client-sided shaders that are visual only, and cannot by themselves do anything beyond apply an effect on screen.

This command is undeniably the most powerful command concerning visual elements. However, it is (in my opinion) the *hardest* to use, especially if you want to make your own post effects.

You see, custom post effects can basically allow you to put whatever you want on the screen; stacking post effects were even used to display data, such as in a minimap (the minimap obviously wasn't terrain accurate though). However, to most people, creating shaders are quite terrifying, and requires knowledge on how shaders actually work, and how to use OpenGL Shader Language. 

Overall, this command is a double-eged sword, because it can lead to basically infinite possibilities (at least for the client's screen), but shaders are some of the hardest things to work with in vanilla Minecraft. For these reasons, `/posteffect` will be given into **B+ tier**, since it is the most powerful command concerning visual effects, but is likely the hardest to utilize; so much so, that you likely won't ever use it. 

Please note that this is the most unsure placement on the entire list <!--This is unlikely to be, but possibly can be subject to change-->, since the balancing potenital and usability is especially hard here.