# Mac specsific

1. Install pass

    ```bash
    brew install pass pinentry-mac

    echo "pinentry-program /usr/local/bin/pinentry-mac" >> ~/.gnupg/gpg-agent.conf

    gpgconf --kill gpg-agent

    defaults write org.gpgtools.common UseKeychain -bool NO
    ```

1. Install pass-simple

    ```bash
    brew install --cask shemeshg/homebrew-tap/pass-simple
    ```
1. Dark mode, looks bad with default QML macos style.

    ```
    defaults write PassSimple.shemeshg.com NSRequiresAquaSystemAppearance -bool Yes
    ```

1. Mac has no `/dev/shm` you can create temporary ram drive after every boot with.

    ```bash
    diskutil erasevolume HFS+ RAM_Disk_4G `hdiutil attach -nomount ram://8192000`
    ```


## dev packages

```bash
brew install gpgme libgpg-error pinentry-mac yaml-cpp
```