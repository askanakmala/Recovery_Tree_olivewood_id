# Device configuration for Xiaomi Redmi 8a pro

The Redmi 8a Pro (codenamed _"olivewood"_) is a smartphone from Xiaomi.
It was released in April 2020.

<p align="center">
  <a href="#compile">⚙️ Compile</a> •
  <a href="#test">💡 Test</a> •
  <a href="#specification">📱 Specification</a> •
</p>

![r8ap](https://github.com/askanakmala/template_me/blob/main/r8ap.jpg "r8ap")

## Compile

First sync PBRP manifest:

```
repo init -u git://github.com/PitchBlackRecoveryProject/manifest_pb.git -b twrp-9.0
```
Then add these string to .repo/manifests/remove.xml


Then add these projects to .repo/local_manifests/roomservice.xml (If you don't have it, you can add them to .repo/manifest.xml): 

```xml
<project name="askanakmala/android_device_xiaomi_olivewood-twrp" path="device/xiaomi/olivewood" remote="github" revision="PBRP_9.0-Q" />
```

Now you can sync your source:

```
repo sync
```

To auotomatic make the twrp installer, you need to import this commit in the build/make path: https://gerrit.omnirom.org/#/c/android_build/+/33182/

Finally execute these:

```
. build/envsetup.sh
export ALLOW_MISSING_DEPENDENCIES=true
export LC_ALL=C
lunch omni_olivewood-eng 
mka recoveryimage 
```

## Test

To test it:

```
fastboot boot out/target/product/olivewood/recovery.img
```

## Specification

Basic   | Spec Sheet
-------:|:-------------------------
CPU     | Octa-core (4x1.95 GHz Cortex-A53 & 4x1.45 GHz Cortex A53)
CHIPSET | Qualcomm SDM439 Snapdragon 439 (12 nm)
GPU     | Adreno 505
Memory  | 2/3 GB
Shipped Android Version | 9.0 update to 10.0
Storage | 32 GB
MicroSD | Up to 512 GB
Battery | 5000 mAh (non-removable)
Display | 720 x 1520 pixels, 19:9 ratio (~270 ppi density)
Rear Camera  | 13 MP, f/2.2, (wide), 1/3.1", 1.12µm, PDAF
Rear Depth Sensor  | 2 MP, f/2.4, (depth)
Front Camera | 8 MP, f/2.0, 1/4", 1.12µm
Release Date | 02 April 2020
