# Saltrole
Sets moderator and administrator roles for Salt.
## Permissions
```js
global.saltrole: {
    global.saltrole.*, //All
    global.saltrole.mod,
    global.saltrole.admin
}
```
## +saltrole {type} {name}
Sets a role to be the saltrole of the given type. So far valid types are `moderator` for moderator roles and `administrator` for administrator roles. The name is case insensitive.