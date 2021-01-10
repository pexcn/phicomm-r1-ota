# Phicomm R1 OTA

## Usage

```bash
# adb connect to phicomm r1
adb connect <phicomm-r1-ip-address>:5555

# get current version
adb shell "cat /system/build.prop | grep ro.build.version.incremental"

# choose the correct version to update
wget https://pexcn.github.io/phicomm-r1-ota/otaprop/ota-<current-version>-<target-version>.txt
adb push ota-<current-version>-<target-version>.txt /sdcard/otaprop.txt
adb reboot

# cleanup after updated
rm ota-<current-version>-<target-version>.txt
adb shell rm /sdcard/otaprop.txt
```
