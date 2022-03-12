# banned-rooms

An encrypted list of banned Matrix rooms.

# Decryption

This list needs to be decrypted, contact @michael:perthchat.org for the password if you're a public server owner who would like to use this list.

`$ openssl enc -aes-256-cbc -d -pbkdf2 -in banned-rooms.txt.enc -out banned-rooms.txt`

# Encryption

To make a pull request for this list, you'll first want to encrypt it with the same password:

`$ openssl enc -aes-256-cbc -pbkdf2 -in banned-rooms.txt -out banned-rooms.txt.enc`

Then remove the unencrypted copy before you commit:

`$ rm banned-rooms.txt`
