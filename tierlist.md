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