# Windows specific

Windows runs natively with `Rnpgp` and `gnupg` backend.
Backup your `gnupg` keys before converting from `sqlite` to `kbx`.

## install software

1. install `gopass`

    ```
    winget install Git.Git
    winget install GnuPG.Gpg4win
    winget install gopass.gopass
    ```



    <https://github.com/gopasspw/gopass/blob/master/docs/setup.md>

1. initialize `gopass` with `gopass setup`


1. list keys, and inspect store location and key format.

   `gpg --list-keys`

1. convert `gpg4win` `sqlite` to `kbx` using `gpg-disable-keyboxd`.

    <https://gpg4win.org/version4.2.html>

1. use `gopass` to create and edit a test document.

1. Remove previous `winget` executable  

    ```
    winget remove Shemeshg.PassSimple
    ```

    install scoop if not installed

    ```
    Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
    irm get.scoop.sh | iex
    ```

    add the bucket
    ```
    scoop bucket add extras
    scoop bucket add shemeshg https://github.com/shemeshg/scoop-bucket
    ```

    install
    ```
    scoop install pass-simple
    ```

    keep updated with
    ```
    scoop update *
    ```


1. Windows Os does not recognize `dot` initial as `hidden`, so at the root of the repository.

```
Get-ChildItem -Path . -Force -Filter ".*" | ForEach-Object { $_.Attributes = 'Hidden' }
```