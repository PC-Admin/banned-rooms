# banned-rooms

An encrypted list of banned Matrix rooms.

# Decryption

This list needs to be decrypted, contact [@michael:perthchat.org](https://matrix.to/#/@michael:perthchat.org) for the password if you're a public server owner who would like to use this list.

`$ openssl enc -aes-256-cbc -d -pbkdf2 -in banned-rooms.txt.enc -out banned-rooms.txt`

# Encryption

To make a pull request for this list, you'll first want to encrypt it with the same password:

`$ openssl enc -aes-256-cbc -pbkdf2 -in banned-rooms.txt -out banned-rooms.txt.enc`

Then remove the unencrypted copy before you commit:

`$ rm banned-rooms.txt`

# How To

Blocking all these rooms manually will take a long time, to speed the process up, remove the `# xxx` category headers from the list and use my moderation script to delete these rooms automatically: 

[pc-admins-synapse-moderation-tool](https://gitlab.com/PC-Admin/pc-admins-synapse-moderation-tool)

Example:

```
20
Delete multiple rooms selected

Please enter the path of the file containing a newline seperated list of room ids: ./banned-rooms.txt  

Please enter the local username that will create a 'muted violation room' for your users (Example: michael): mod_team     

Please enter the room name of the muted violation room your users will be sent to: COC VIOLATION

Please enter the shutdown message that will be displayed to users: KNOCK KNOCK, OPEN UP ITS THE FBI!

 Do you want to purge these rooms? (This deletes all the room history from your database.) y/n? y

 Do you want to block these rooms? (This prevents your server users re-entering the room.) y/n? y

...

Are you sure you want to purge and block these rooms? y/n? y
```
