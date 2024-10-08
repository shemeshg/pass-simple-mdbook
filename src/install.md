# install platform specific

* [install_linux](install_linux.md)
* [install_mac](install_mac.md)
* [install_windows](install_windows.md)

## For all platforms - recommended

* Rnp do not self sign your Id, so import public ID in `pass-simple` using `gnupg` mode.

  On windows `gnupg` mode not applicable, so:

  ```bash
  $ gpg --edit-key jane@acme.org
  gpg> lsign
  gpg> y
  gpg> save
  ```

* On windows use `gopass` instead of `pass`.

## Mandatory

1. Create a note with pass command line, ensure all well

    ```bash
    pass
    pass edit whatever
    ```

    * If pass store not initialized use `gopass setup` or follow this:
    <https://www.redhat.com/sysadmin/management-password-store>

      This document will walk through creating Private and public keys, and init the repository (setup the `.gpgid` authorization file).

2. Ensure you can read and write the test note created before.

3. setup git

    Avoid this set by using `gopass clone`

- if not using `gopass`.

    Prefer manually to ensure `gpg` absolute path, also mandatory after `git clone`.

    ```bash
    # New repository
    git init  
    echo '*.gpg diff=gpg' > ".gitattributes"
    # New and Cloned repository
    git config --local diff.gpg.binary true
    git config --local diff.gpg.textconv "`which gpg` -d --quiet --yes --compress-algo=none --no-encrypt-to"
    ```
    Or using pass, and correct the `diff.gpg.textconv` with above.

    ```bash
    export PASSWORD_STORE_DIR=/Volumes/volume\ name/password-store
    pass git init
    ```

4. Ensure you can `git commit -am "commit"`.

5. create additional change and ensure you can `git diff HEAD~` and see last change in clear text.

6. Set `restoreWindows` in `vscode` to `folder` or `none`

    It is always good practice to close all `vscode` opened tabs before closing `pass simple`
    otherwise `vscode` might recreate temporary files edited.

## Optional/Advanced

1. Protect your '.gpg_id' or specific folders with Git-Enforced Policy (`git server and client hooks`)

    <https://git-scm.com/book/en/v2/Customizing-Git-An-Example-Git-Enforced-Policy>

1. Use disk encryption - `tomb`/`veracrypt` or mac's `diskutil` to protect the repository itself.

    password for the disk encryption can be stored in the default repository (`~/.password-store/`), and then link mounted encrypted repository with `ln -s` (like `mounts` in `gopass`)

1. Consider using `yubikey` or [move secret keys to USB drive](https://gpgtools.tenderapp.com/kb/gpg-keychain-faq/how-to-move-secret-keys-to-usb-drive)

    Use rotate [subkey](https://help.ubuntu.com/community/GnuPrivacyGuardHowto) for different devices,
    or [ASDK](https://www.gnupg.org/blog/20230321-adsk.html) for team members.

1. Backup your store to other drive or remote ssh server

    <https://stackoverflow.com/questions/39471072/how-to-create-a-local-push-destination-on-a-hard-disk-using-git>

    Ensure you can `git pull` and `git push`

1. protect application configuration file as readonly with `chmod`, or
[AppArmor](https://ubuntu.com/server/docs/security-apparmor)
