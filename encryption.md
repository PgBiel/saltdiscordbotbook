# Encryption
An intricate private/public key encryption system used to keep your messages safe! Private keys are used to decrypt messages and public keys are used to encrypt them.
## +setkey {key}
Used to set your private key and get a public key. It will send a copy of your private key to your DM. **KEEP IT SAFE**

Example: `+setkey bananas` - Sets your private key to "bananas" and generates a public key.
## +getkey {user}
Used to get the public key of a user to encrypt messages.

Example: `+getkey @Aplet123#9551` - Gets Aplet123's public key.
## +encrypt 