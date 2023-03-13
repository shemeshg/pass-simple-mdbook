# Ubuntu specsific

1. Install dependencies

    ```bash
    suto apt-get -y  install pass gnupg2 libyaml-cpp-dev libgpgme-dev libgpgmepp-dev
    ```

    This is required if you compile yourself, or download the static linked.

2. Create menu shortcut, see `pass-simple.desktop`.
3. Try your luck make `ydotool` autotype.

    Manual compilation <https://askubuntu.com/questions/1413829/how-can-i-install-the-latest-ydotool-1-0-1-keyboard-automation-tool-working-on> 
    will get ydotool work under root only.

    See `setting` tab in `pass-simple`, and set autotype accordingly.

## If downlaoding the staticlly deployed zip file from sourceforge

1. Extract the zip file.

2. run the executable

3. Create desktop shortcut

## If compile yourself

1. install qt <https://web.stanford.edu/dept/cs_edu/resources/qt/install-linux>

    Notice: Qt6 packages in the deb repository are broken, so download the install from Qt.com

2. pull submodules

    <https://stackoverflow.com/questions/1030169/pull-latest-changes-for-all-git-submodules>

3. `qt-cmake` and build.

    ```bash
    ~/Qt/6.5.0/gcc_64/bin/qt-cmake -DCMAKE_BUILD_TYPE=Release ../pass-simple-qt/
    cmake --build .
    ```

