# Ubuntu specific

The `.deb` file and the `.zip` files are already `qt-deployed`.
If you are using other distro like `Fedora`, you can extract the contents of the `.deb` file or download the linux `zip`, extract it to `/opt` and run.


1. Download the deb file and install 

    ```bash
    sudo dpkg -r pass-simple
    sudo dpkg -i ./pass-simple-1.x.x-Linux.deb    
    ```

    on ubuntu 24.04 `sudo apt --fix-broken install` and repeat.

1. Install dependencies if compile yourself (or not using the deb file)

    ```bash
    sudo apt-get -y  install pass gnupg2 libgpgme-dev libgpgmepp-dev libbz2-dev libjson-c-dev
    ``` 

1. `Ubuntu ARM` might not have `botan-2-dev` so install `botan`
    
    ```bash
    sudo apt-get -y  install botan-2-dev
    ```    

    or

    ```bash
    sudo apt-get -y  install botan
    ```

1. `Ubuntu` comes without utf-8 fonts so 

    ```bash
    sudo apt install fonts-noto fonts-noto-cjk fonts-noto-color-emoji fonts-noto-core
    ```

1. Install `ydotool` autotype.

    For Manual compilation <https://askubuntu.com/questions/1413829/how-can-i-install-the-latest-ydotool-1-0-1-keyboard-automation-tool-working-on>

- `sudo cp /usr/lib/systemd/user/ydotoold.service /etc/systemd/system`
- `sudo service ydotool start`
- `sudo systemctl enable ydotool`
- ensure `export YDOTOOL_SOCKET=/tmp/.ydotool_socket` in `/opt/pass-simple/bin/pass-simple.sh`.

- Open `pass-simple` and select `setting`.

    set autotype to

    ```bash
    ydotool type sequence
    ```

## If compile yourself

1. If compile `rnpgp` yourself follow <https://www.rnpgp.org/software/rnp/docs/installation/> and install the `botan` version as requested in the document.

1. install qt <https://web.stanford.edu/dept/cs_edu/resources/qt/install-linux>

    Notice: Qt6 packages in the deb repository are broken, so download the install from Qt.com

2. pull submodules

    <https://stackoverflow.com/questions/1030169/pull-latest-changes-for-all-git-submodules>

4. `qt-cmake` and build.

    ```bash
    ~/Qt/6.5.0/gcc_64/bin/qt-cmake -DCMAKE_BUILD_TYPE=Release ../pass-simple-qt/
    cmake --build .
    ```

