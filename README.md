# twrp for Realme RMX3261 Android 11 stock
twrp builds https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp and works after build.
These twrp sources were used for porting https://github.com/allex2/android_device_alldocube_T1020S.
## Getting Started ##
---------------

To get started with AOSP sources to build TWRP, you'll need to get familiar
with [Git and Repo](https://source.android.com/source/using-repo.html).

To initialize your local repository using the AOSP trees to build TWRP, use a command like this:

    repo init -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-11

To initialize a shallow clone, which will save even more space, use a command like this:

    repo init --depth=1 -u https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git -b twrp-11

Then to sync up:

    repo sync
Clone this device:

    git clone https://github.com/DragonWarriorJS/android_device_RMX3261_11_A.79 -b device/realme/RMX3261

NOTE: Device makefile in the device tree and dependencies file should use the "twrp" prefix.

Then to build for a device with recovery partition:

     cd <source-dir>; export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch twrp_<device>-eng; mka recoveryimage

Then to build for a device without recovery partition:

     cd <source-dir>; export ALLOW_MISSING_DEPENDENCIES=true; . build/envsetup.sh; lunch twrp_<device>-eng; mka bootimage

