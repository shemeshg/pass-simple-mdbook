# install platform specific

* [install_linux](install_linux.md)
* [install_mac](install_mac.md)
* [install_windows](install_windows.md)

## For all platforms - recommended

1. Create a note with pass command line, ensure all well

    ```bash
    pass
    pass edit whatever
    ```

    * If pass store not initialized, follow this:
    <https://www.redhat.com/sysadmin/management-password-store>

      This document will walk through creating Private and public keys, and init the repository (setup the `.gpgid` authorization file).

1. Ensure you can read and write the test note created before.

1. setup git

    ```bash
    export PASSWORD_STORE_DIR=/Volumes/volume\ name/password-store
    pass git init
    ```

    or do it manually with

    ```bash
    git init
    echo '*.gpg diff=gpg' > ".gitattributes"
    git config --local diff.gpg.binary true
    git config --local diff.gpg.textconv "gpg -d --quiet --yes --compress-algo=none --no-encrypt-to"
    ```

1. Ensure you can `git commit -am "commit"`.

1. create additional change and ensure you can `git diff ~1` and see last change in clear text.

1. Set `restoreWindows` in `vscode` to `folder` or `none`

    It is always good practice to close all `vscode` opened tabs before closing `pass simple`
    otherwise `vscode` might recreate temporary files edited.

Optional/Advanced

1. Protect your '.gpg_id' or specific folders with Git-Enforced Policy (`git server and client hooks`)

    <https://git-scm.com/book/en/v2/Customizing-Git-An-Example-Git-Enforced-Policy>

1. Consider using `yubikey` or [move secret keys to USB drive](https://gpgtools.tenderapp.com/kb/gpg-keychain-faq/how-to-move-secret-keys-to-usb-drive)


1. Backup your store to other drive or remote ssh server

    <https://stackoverflow.com/questions/39471072/how-to-create-a-local-push-destination-on-a-hard-disk-using-git>

1. Ensure you can `git pull` and `git push`    