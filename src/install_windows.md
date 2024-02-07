# Windows specific

Windows runs natively with `Rnpgp` and `gnupg` backend.
Backup your `gnupg` keys before converting from `sqlite` to `kbx`.

## install software

1. install `gpg4win`

    `winget install gpg4win`

1. install chocolatey (via copy past into PowerShell)

    <https://chocolatey.org/install>

1. install `gopass`

   `choco install gopass`

    <https://github.com/gopasspw/gopass/blob/master/docs/setup.md>

1. initialize `gopass` with `gopass setup`


1. list keys, and inspect store location and key format.

   `gpg --list-keys`

1. convert `gpg4win` `sqlite` to `kbx` using `gpg-disable-keyboxd`.

    <https://gpg4win.org/version4.2.html>

1. use `gopass` to create and edit a test document.

1. Extract the deployed windows zip folder, and run `pass-simple.exe` from windows explorer. (application is not signed, so confirm security screen).
