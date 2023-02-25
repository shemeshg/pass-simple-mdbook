# install platform specific

* [install_linux](install_linux.md)
* [install_mac](install_mac.md)

## For all platforms

1. Create a note with pass command line, ensure all well

    ```bash
    pass
    pass edit whatever
    ```

    * If pass is not ok, follow this:
    <https://www.redhat.com/sysadmin/management-password-store>

      This document will walk through creating Private and public keys, and init the repository (setup the `.gpgid` authorization file).

2. Ensure you can read and write the test note created before.

3. setup git

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

3. Ensure you can `git commit -am "commit"`.

4. create additional change and ensure you can `git diff`.

5. Backup your store to other drive

    https://stackoverflow.com/questions/39471072/how-to-create-a-local-push-destination-on-a-hard-disk-using-git

6. Ensure you can `git pull` and `git push`

