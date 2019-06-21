# android_device_xiaomi_andromeda
For building TWRP for Xiaomi Mi Mix 3 5G

TWRP device tree for Xiaomi Mi Mix 3 5G

## Features

Works:

- ADB
- Decryption of /data (Only if pattern or pin or password is not setted)
- Screen brightness settings
- Correct screenshot color
- MTP
- Flashing (opengapps, roms, images and so on)
- Backup/Restore (Needs more testing)
- USB OTG


TO-DO:

- Vibration support

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-9.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/andromeda" name="mauronofrio/android_device_xiaomi_andromeda" remote="github" revision="android-9.0" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_andromeda-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/andromeda/recovery.img
```

## Other Sources

Kernel Sources: using precompiled stock kernel

## Thanks

- Thanks to @PeterCxy for the commits and the base: https://github.com/PeterCxy/android_device_xiaomi_violet-twrp
