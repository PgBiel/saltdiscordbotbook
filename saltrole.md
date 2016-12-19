# Saltrole
Sets moderator and administrator roles for Salt.
## Permissions
```js
saltrole: {
    global.saltrole.*, //All
    global.saltrole.moderator,
    global.saltrole.administrator
},
delsaltrole: {
    global.delsaltrole.*, //All
    global.delsaltrole.moderator,
    global.delsaltrole.administrator
}
```
## +saltrole {type} {name}
Sets a role to be the saltrole of the given type. So far valid types are `moderator` for moderator roles and `administrator` for administrator roles. The name is case insensitive.
## +delsaltrole {type}
Deletes the saltrole for the specified type.
## Permission Nodes
Saltroles grant access to certain commands, however if a permission node rejects access to it, then you may still not use it. For example, if you have `-global.mute` but have the `moderator` role you still cannot use [`+mute`](./mute.md).

The `moderator` role grants access to the following commands:
```js
+mute,
+unmute,
+pmute,
+warn,
+clearwarns
```
The `administrator` role grants access to the following commands:
```js
+logs,
+saltrole,
+delsaltrole,
+actionlogs,
+role,
+setwarns,
+manageselfrole,
+prefix
```