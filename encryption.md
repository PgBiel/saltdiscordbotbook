# Encryption
An intricate private/public key encryption system used to keep your messages safe! Private keys are used to decrypt messages and public keys are used to encrypt them.
## +setkey {key}
**USABLE IN PM**

Used to set your private key and get a public key. It will send a copy of your private key to your DM. **KEEP IT SAFE**

Example: `+setkey bananas` - Sets your private key to "bananas" and generates a public key.
## +getkey {user}
Used to get the public key of a user to encrypt messages.

Example: `+getkey @Aplet123#9551` - Gets Aplet123's public key.
## +encrypt [FLAGS] (public key) {text}
Used to encrypt text. **Note that you must keep the `[](){}` for it to work.** `FLAG` is a comma-separated list of flags, where the possible flags are `KEEP` to keep the message instead of deleting it and `PM` to send the result to PM.

## +decrypt [FLAGS] (private key) {text}
Used to encrypt text. **Note that you must keep the `[](){}` for it to work.** `FLAG` is a comma-separated list of flags, where the possible flags are `KEEP` to keep the message instead of deleting it and `PM` to send the result to PM.