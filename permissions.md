#Permissions
Permissions are an interesting topic, which lets you control the usage of Salt to the max. Disabling commands are covered in the [other article](./disabling-commands.md).

##What are they?
Let's take a look at the list of permissions (link [here](http://pastebin.com/e5UAqaib)).
They seem very complicated, don't they? Well, let's cover that here.

![Top of the Permission list](http://image.prntscr.com/image/c8922cf6959d45e397efda9be723f13a.png)
That's the top of the permission list. Is it too confusing to understand? I get you. It's pretty simple, actually. The `permList = {` part at the top indicates the start of permList (Permission list), and the `}` right after all permissions indicates the end. There's a format: `command_name: "permission.node"`.

- `command_name`: Name of the command, indicating what that permission is for. The only exceptions for this are `all`, `globalall` and `customall` (each of them indicate "All permissions", "All global permissions" and "All custom permissions", respectively. We'll talk about the categories (`global` and `custom`) later in this article).
- `permission.node`: The permission node. A permission node is the representation of a permission, and we tried to make it as simple as it could be. Keep reading, and you'll get all of it!

So, you get it now? No? Let's take for example that line from the permission list:
```js
kick: "global.kick",
```
In that line, the word "kick:" is the command (`kick`) and the `global.kick` is the permission node! Therefore the permission node for the `kick` command is `global.kick`. Simple?

Then to give it to someone just do: `+p giveuser global.kick @UserMentionGoesHere#0000`. Simple!

**Note:** Don't forget that you can also give permissions to roles! With this example, you would do: `+p giverole global.kick RoleNameGoesHere`. However, **user permissions always override role permissions.** Keep that in mind.

At the bottom at the permission list page, you may see a bunch of permissions above each other, without following the format of `command_name: permission.node`. Those are the **default permissions**: Permissions that users always have unless you negate them.
##+p and Permissions
```md
**Syntax:**
+p <action> <argument 1> <argument 2>
```
`+p` is the command to give permissions to someone or a role, to disable or enable commands, and to take permissions.
However, note that taking permissions is simply deleting whatever is stored for that permission node, and **NOT** disabling it. To make someone unable to do `+kick` regardless of permissions, for example, you do `+p giveuser -global.kick @UserGoesHere#0000` and **NOT** `+p takeuser`.  Notice how, at that giveuser command, I inserted a `-` behind the permission node. That's called **negating the permission node**. And, to remove the negation, I do `+p takeuser global.kick @UserGoesHere#0000`. Hard to understand? Let's make an example.

Let's say there's this guy named **Bob** in my server. He's a really chill moderator, and then he suddenly started kicking people for no reason, using Salt. So I think, _"hmm, what if I make him unable to do +kick?"_. What I do? I send this command:
```md
+p giveuser -global.kick @Bob#0000
```
Done! Now he cannot do `+kick`.

Now after a while, he has calmed down and I want him to be able to do `+kick` again. What do I do? I send this:
```md
+p takeuser global.kick @Bob#0000
```
Done! Now I removed his `global.kick` negation. Now he will be able to use `+kick` as long as he has the permission `Kick Members` (of Discord). Neat!

Other usages for `+p` can be `+p list` (get a link for listing all permission nodes, or you can click [here](http://pastebin.com/e5UAqaib)) and `+p disable`, `+p enable` & `+p clone`, those 3 are about disabling and enabling commands, which will be spoken about in [this other article](./disabling-commands.md).

**Note:** The `+p` command has permissions by itself too!
- `global.p.*` -> Grants access to all `+p` actions.
- `global.p.give` -> Grants access to `+p giveuser` and `+p giverole`.
- `global.p.take` -> Grants access to `+p takeuser` and `+p takerole`.
- `global.p.disable` -> Grants access to `+p disable` and `+p clone`.
- `global.p.enable` -> Grants access to `+p enable`.

**Note 2:** To view list of Salt Permissions for a role or user, do `+listperms role/user RoleNameOrUserMention` (If using the `user` option, you can put nothing after it to see your own). Not to be confounded with the command `+perms`, to list Discord permissions.

Now let's switch the topic. Permissions. Why do I see `global.` in the start of all permission nodes in there [at the permission list]? Well, because of custom commands. Let me show you.

There are 2 prefixes: `global` and `custom`. **Any** _valid_ permission node that starts with `global` is a permission node for a command implemented by Salt himself. If it starts with `custom`, though, it's a custom command.

Let me give you an example to explain this. Let's say that, in a server, the owner makes a custom command named `die`.  And he wants the `die` command to be only used by people with the role `Admin`. How can he do that? It's pretty simple.

All custom commands have permission nodes. It's `custom.commandname` (replace commandname with the custom command's name, of course. Oh, and spaces in the custom command's name must be replaced by an underline (`_`)).


So, first, we negate the permission from the @everyone role:
```md
+p giverole -custom.die everyone
```
Then, we give the permission to the `Admin`  role:
```md
+p giverole custom.die Admin
```
And it's done! See the difference between the `global` and `custom` prefixes? `global` means command implemented by Salt and `custom` means a custom command (user-made).
##Troubleshooting
1. **Their role negates `xx.xx.xx` permission, yet they still have it!** -> Check the permissions for higher roles (if he has any), and also check his user permissions: User permissions **ALWAYS** override role permissions.
2. **What about `+p disable`, `+p enable` and `+p clone`? I don't see them anywhere in this article.** -> Like I said, there's another article for it (click [here](./disabling-commands.md)).  
  
    
      
      