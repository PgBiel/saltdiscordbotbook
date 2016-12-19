# Encryption
An intricate private/public key encryption system used to keep your messages safe! Private keys are used to decrypt messages and public keys are used to encrypt them.
## Permissions
```js
setkey: global.setkey,
getkey: global.getKey,
encrypt: global.encrypt,
decrypt: global.decrypt
``` 
## +setkey {key}
**USABLE IN PM**

Used to set your private key and get a public key. It will send a copy of your private key to your DM. **KEEP IT SAFE**

Example: `+setkey bananas` - Sets your private key to "bananas" and generates a public key.
## +getkey {user}
Used to get the public key of a user to encrypt messages.

Example: `+getkey @Aplet123#9551` - Gets Aplet123's public key.
## +encrypt [FLAGS] (public key) {text}
Used to encrypt text. **Note that you must keep the `[](){}` for it to work.** `FLAG` is a comma-separated list of flags, where the possible flags are `KEEP` to keep the message instead of deleting it and `PM` to send the result to PM. **Note that if public key is kept empty(`()`), it will use your public key.**

Example: `+encrypt [PM] () {apple}` - Encrypts `apple` with your public key and sends it to PM.

## +decrypt [private key] {text}
Used to decrypt text. **Note that you must keep the `[]{}` for it to work and that if public key is kept empty(`()`), it will use your public key.**

Example: `+decrypt [] {ljfjjnl}` - Decrypts `ljfjjnl` with your private key. 