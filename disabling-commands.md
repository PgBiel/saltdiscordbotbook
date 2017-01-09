#Disabling and Enabling commands
A core feature for Salt. Before reading this, I recommend you read the [Permissions](./permissions.md) article.
####Permissions
* `global.p.disable` -> Grants access to the `+p disable` and `+p clone` commands.
* `global.p.enable` -> Grants access to the `+p enable` command.

##What IS this?!?!?!
The name is kind of obvious really, but let's get going. With Salt, you can disable commands for the whole server, and just for a channel. However, you can also clone disabled commands from another channel! Isn't it cool?

##Okay! How do I use it?
`+p disable/enable server/channel commandname`

Replace `commandname` with the command's name! (Also valid for custom commands :D)

Let's make an example here. Let's say there's a server, where you want people to not use `+feedme` in the whole server (Yeah I know it's an useless command but anyway :P). What to do?
```md
+p disable server feedme
```
Done! Now nobody can use `+feedme` in your server.

But of course, if you want to enable it again, just do:
```md
+p enable server feedme
```
Voi-la! Now people can use `+feedme` again.

##I want to copy the list of disabled commands from another channel!
That's entirely possible. Do not waste your time writing `+p disable` or `+p enable` for each command! You can just do the super, ultra, mega, ultimate COMMAND:
```md
+p clone #channel
```
Simple, right? It will clone the disabled commands of the #channel specified there, to the channel you're currently speaking at. Cool, right?

**WARNING!** Be careful. If you clone from a channel that has no disables, it will make it so the channel you are speaking at will have **no disables** either! Make sure to see the full list of disables using the command below.

##How do I list all disabled commands?
Simple enough, it's this command right here:
```md
+listdisables server/channel
```
Perfect!

##Special Commands!
There are certain commands that can not be disabled, however, will have a different behavior on disabling. Those are:
- **+help** -> Doesn't actually have a different behavior, just _can't_ be disabled.
- **+info bot** -> If the permission for +info bot is negated, or the +info command is disabled, it'll send it on DMs instead.
- **+contact** -> Makes it go to DMs instead.