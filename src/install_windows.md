# Windows specific

Windows runs natively with `Rnpgp` and `gnupg` backend.
Backup your `gnupg` keys before converting from `sqlite` to `kbx`

## Fix known bugs

- gopass `.gpgid` key format after `gopass setup` is none standard, so empty the file.
- Zip will notify of 2 files it can not extract, you can safely ignore that.
  
  (This is because the deployment was not through `cpack ZIP`  but manually `qtdeploy` because of a bug)

## install software

1. install `gpg4win`

    `winget install gpg4win`

1. install chocolatey (via copy past into PowerShell)

    <https://chocolatey.org/install>

1. install `gopass`

   `choco install gopass`

    <https://github.com/gopasspw/gopass/blob/master/docs/setup.md>

2. initialize `gopass` with `gopass setup`

3. empty `.gpgid` file with none standard key id format.

4. list keys, and inspect store location and key format.

   `gpg --list-keys`

5. convert `gpg4win` `sqlite` to `kbx` using `gpg-disable-keyboxd`.

    <https://gpg4win.org/version4.2.html>

6. use `gopass` to create and edit a test document.

7. Extract the deployed windows zip folder, and run `pass-simple.exe` from windows explorer. (application is not signed, so confirm security screen).
