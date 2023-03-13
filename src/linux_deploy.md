# build and deploy

## Setup environment

[linux_setup](linux_setup.md)

## shared compilation

```bash
~/Qt/6.2.4/gcc_64/bin/qt-cmake -DCMAKE_BUILD_TYPE=Release ../pass-simple-qt/
cmake --build .
```

## static compilation

```bash
mkdir Ubuntu20.04StaticFolderVer0.25
cd Ubuntu20.04StaticFolderVer0.25/
 /home/ubuntu/Qt6.42Static/bin/qt-cmake  -DCMAKE_BUILD_TYPE=Release ../pass-simple-qt/
cmake --build .
cd ..
zip -r Ubuntu20.04StaticFolderVer0.25.zip Ubuntu20.04StaticFolderVer0.25

````