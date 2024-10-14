# Mac specific

1. Install pass

    ```bash
    brew install pass pinentry-mac

    echo "pinentry-program `which pinentry-mac`" >> ~/.gnupg/gpg-agent.conf

    gpgconf --kill gpg-agent

    defaults write org.gpgtools.common UseKeychain -bool NO
    ```

1. Install pass-simple

    ```bash
    brew install --cask shemeshg/homebrew-tap/pass-simple
    ```

1. "XYZ Is Damaged and Can’t Be Opened. You Should Move It To The Trash"

    See https://discussions.apple.com/thread/253714860?sortBy=rank

    ```
    xattr -c /Applications/pass-simple.app/
    ```

2. Mac has no `/dev/shm` you can create temporary ram drive after every boot with.

    ```bash
    diskutil erasevolume HFS+ RAM_Disk_4G `hdiutil attach -nomount ram://8192000`
    ```


## dev packages

```bash
brew install gpgme libgpg-error pinentry-mac
brew tap rnpgp/rnp
brew install rnp
```
