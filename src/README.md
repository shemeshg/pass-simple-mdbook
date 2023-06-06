# [pass simple](https://github.com/shemeshg/pass-simple-qt)

Similar to [QtPass](https://github.com/IJHack/QtPass):

Multi-platform GUI for [pass](https://www.passwordstore.org/), the standard unix password manager

<https://sourceforge.net/projects/pass-simple/>

Screenshots: <https://github.com/shemeshg/pass-simple-qt/wiki>

## Markdown

- Markdown is CommonMark plus the GitHub extensions for tables and task lists (see <https://doc.qt.io/qt-6/qml-qtquick-text.html>).

- Inline Images are not supported

- Links with relative path to other `.pgp` in the same `password store` are supported, 

    link should not include the `.pgp` extension, for example 

    ```Md
    # Header

    [ref to a/b file.pgp](<a/b file>)

    or <a/b file>
    ```

## Yaml

- Since `pass simple` store `totp` in `yaml`, to read generated totp use

    ```bash
    gopass show fileName|yq '.["totp"]' | xargs -I {} oathtool -b --totp {}
    ```