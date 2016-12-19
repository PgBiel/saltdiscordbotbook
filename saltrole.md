# Saltrole
Sets moderator and administrator roles for Salt.
## Permissions
```js
saltrole: {
    global.saltrole.*, //All
    global.saltrole.moderator,
    global.saltrole.administrator
}
```
## +saltrole {type} {name}
Sets a role to be the saltrole of the given type. So far valid types are `moderator` for moderator roles and `administrator` for administrator roles. The name is case insensitive.
## Permission Nodes
Saltroles grant pseudo-permission nodes, however regular permission nodes will overwrite it, so if you have `-global.mute` but you have the `moderator` role, you still cannot use [`+mute`](./mute.md).
The `moderator` role grants the following pseudo-permission nodes:
```js
global.mute,
global.unmute,
global.pmute,
global.warn,
global.clearwarns
```