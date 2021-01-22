## Steps to generate GPG Key\
1. `gpg -- full-generate-key`
2. Select option (1) for RSA key and give keysize of 4096
3. Select Press 0 for not to expire key ever
Enter Real Name: OctaCat
Email Address: someone@mail.com
Comment: Github GPG Key
4. Enter passphrase
5. `gpg --list-secret-keys --keyid-format LONG`
sec rsa4096/3AA5C34371567BD2 2021-01-22
`gpg --armor --export 3AA5C34371567BD2`
Prints the GPG key, in ASCII armor format
```-----BEGIN PGP PUBLIC KEY BLOCK-----

-----END PGP PUBLIC KEY BLOCK------```
6. Paste GPG into Github account
7. `git config --global user.signingkey 3AA5C34371567BD2`
8. `git config commit.gpgsign true`
