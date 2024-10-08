# ![Alt text](icon.png) [pass simple](https://github.com/shemeshg/pass-simple-qt)

Multi-platform GUI for [pass](https://www.passwordstore.org/), the standard unix password manager

The advantages of `pass simple` include the use of GPGME (native C++, seamless integration with Security cards) or [rnp](https://github.com/rnpgp/rnp) (realtime,multithreading and windows support), as well as support for YAML and Markdown.

Homepage: <https://sourceforge.net/projects/pass-simple/>

Github and support: <https://github.com/shemeshg/pass-simple-qt>

Screenshots: <https://github.com/shemeshg/pass-simple-qt/wiki>

## Rnp & Security card integration

- create a script that accept `keyId` as parameter.

  ```bash
  #!/bin/sh
  /usr/local/bin/gpg -d /outside/your/password-store/$1.gpg
  ```

- `chmod +x` script name
- Encrypt the `/outside/your/password-store/$1.gpg` where `$1` as your `keyId`.  
  with a content of your password.
- Set `Rnp pass std exec path` in settings, to your script.

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
    gopass show fileName|yq '.["totp"]' | oathtool -b --totp -
    ```
- text starts with `-` or `#` can not be `YAML`, and is considered standard text.

- For YAML compatability with password in first line tools, it is possible to put a dummy null field.

  ```yaml
  _: ~
  user: user1
  password: 12345
  ```

## Fields type

- textedit - supports
  - `autotype` of selected text
  - `MarkDown` read only view
- texteditMasked
- text
- url
- password
- totp
- datetime

## Changing password

`Autotype` types the last **saved** value.

After duplicate current filed with an "OLD_" prefix ("OLD_password") in `edit field type`, remember to save.


# R.click tree view

(Not git aware)

- Add folder.
- Delete selected.
- Rename selected.
- Move selected using drag and drop.
  
  `move` available only within the same `.gpg` authorization folder. 

# Case insensitive search

- Default search is case-sensitive (using `std::find`). To make it case-insensitive, add an additional `.*` to the regex.

For example: `.*WhatEver.*.*` (beware of the `std::regex` bug in Linux `gcc 14`).

