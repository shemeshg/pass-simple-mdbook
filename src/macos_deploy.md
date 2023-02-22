# pass simple  deploy macos

```bash
cd build-pass-simple-qt-Qt_6_4_2_for_macOS-Release/

 /Volumes/FAST/Qt/6.4.2/macos/bin/macdeployqt Pass\ simple.app -qmldir=/Volumes/RAM_Disk_4G/pass-simple -dmg

change name to  pass-simple-osx_0.30.0.dmg

sftp iuqwer9@frs.sourceforge.net
sftp> cd /home/frs/project/pass-simple
sftp> put pass-simple-osx_0.30.0.dmg

sha256sum pass-simple-osx_0.30.0.dmg

cd /Volumes/FAST/develop/homebrew-tap/Casks/

code .
```
