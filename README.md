# 3ds-libsidplay
port of libsidplay 1.36.60 by Michael Schwendt and others to Nintendo 3DS

## Installation
In devkitARM install via pacman
```
pacman -S 3ds-libsidplay
```

## Compiling
You need devkitARM and pkg-config & devkitpro-pkgbuild-helpers to compile (pacman -Sy pkg-config devkitpro-pkgbuild-helpers).

The following commands will install libsidplay to /opt/devkitpro/portlibs/3ds (on Windows MSYS2 - on linux leave out the ```--build``` option in ```configure```)
```
tar xzf libsidplay-1.36.60.tar.gz
cd libsidplay-1.36.60
patch -p0 -i ../libsidplay-1.36.60.patch
source /opt/devkitpro/3dsvars.sh
./configure --host=arm-none-eabi --build=x86 --target=arm-none-eabi --prefix=/opt/devkitpro/portlibs/3ds
make install
```
