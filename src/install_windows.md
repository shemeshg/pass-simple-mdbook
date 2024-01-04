# Windows specific

Windows runs natively with `Rnpgp` and `gnupg` backend.
Backup your `gnupg` keys before converting from `sqlite` to `kbx`

1. install `gpg4win`

    `winget install gpg4win`

1. install chocolatey

    https://chocolatey.org/install

1. install `gopass`

    https://github.com/gopasspw/gopass/blob/master/docs/setup.md

1. convert `gpg4win` `sqlite` to `kbx` useing `gpg-disable-keyboxd`.

    https://gpg4win.org/version4.2.html

1. init you `gopass` store and create a test document.

1. Extract the deployed windows zip folder, and run `pass-simple.exe`
   