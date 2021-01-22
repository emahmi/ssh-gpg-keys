## Steps to generate SSH Key
1. `ssh-keygen -t rsa -b 4096 -C "someone@mail.com"`
2. `Specify the location to save (~/.ssh/id_rsa):` _Press __Enter__ on this step if this where you want to save file_
3. Enter passphrase
4. `eval $(ssh-agent -s)`
5. `ssh-add ~/.ssh/id_rsa`
6. `cat ~/.ssh/id_rsa.pub`<br>
_Copy the contents of the file which displayed_
7. Paste it into github account.


## Steps to generate GPG Key
1. `gpg --full-generate-key`
2. Select option (`1`) for RSA key and give keysize of 4096
3. Select Press `0` for not to expire key ever<br>
_Enter Real Name:_ `OctaCat`<br>
_Email Address:_ `someone@mail.com`<br>
_Comment:_ `Github GPG Key`
4. Enter passphrase
5. `gpg --list-secret-keys --keyid-format LONG`<br>
sec rsa4096/`3AA5C34371567BD2` 2021-01-22<br>
`3AA5C34371567BD2` is key<br>
6. `gpg --armor --export 3AA5C34371567BD2`<br>
Prints the GPG key, in ASCII armor format
```
-----BEGIN PGP PUBLIC KEY BLOCK-----

-----END PGP PUBLIC KEY BLOCK------
```
7. Copy and paste GPG into Github account including `BEGIN PGP` and `END PGP` line
8. `git config --global user.signingkey 3AA5C34371567BD2`
9. `git config commit.gpgsign true`
