# Ubuntu specific

If you are using other distro like `Fedora`, you can extract the contents of the `.deb` file and run the executable. since the `.deb` file is already `qt-deployed`. 

1. Download the deb file and install

1. Install dependencies if compile yourself (not using the deb file)

    ```bash
    suto apt-get -y  install pass gnupg2 libgpgme-dev libgpgmepp-dev
    ```

1. Install `ydotool` autotype.

    For Manual compilation <https://askubuntu.com/questions/1413829/how-can-i-install-the-latest-ydotool-1-0-1-keyboard-automation-tool-working-on> 
    
- `sudo service ydotool start`
- `sudo systemctl enable ydotool`
- ensure `export YDOTOOL_SOCKET=/tmp/.ydotool_socket` in `/opt/pass-simple/bin/pass-simple.sh`.

- Open `pass-simple` and select `setting`. 
    
    set autotype to 
    
    ```bash
    dotool type sequence
    ```

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

