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