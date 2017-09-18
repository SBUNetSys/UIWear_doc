# UIWear Installation Tutorial

## 1. Flash Custom Android AOSP ROM on Nexus 5

**WARNING: Please backup your data before flashing the phone.

### 0) Prerequisites
* **Make sure you have a backup of your Nexus 5 data**
* Ensure you have USB Debugging enabled on your Nexus 5
* Make sure you have installed Android tools on your PC, i.e., adb, fastboot
* Unlock the Nexus 5 by following these steps: https://www.androidpit.com/how-to-unlock-nexus-5-bootloader

### 1) Download ROM files: 

*  **aosp_hammerhead-ota-eng.xujay.zip**: This is our customized ROM which enhances the functionalities of Accessibility mechanism.

*  **BETA-SuperSU-v2.60-20151205163135.zip**: For rooting the phone.

*  **twrp-3.1.1-0-hammerhead.img**: https://dl.twrp.me/hammerhead/twrp-3.1.1-0-hammerhead.img.html

*  Google apps: at http://opengapps.org/. 

### 2) Entering Bootloader mode
* Power off your phone
* Hold the power button, volume up, volume down bottons simultaneously for around 10 seconds
* After then, the phone will reboot into bootloader mode

### 3) Flashing Recovery Environment

Flashing the TWRP recovery environment to your Android phone by using following command
```
fastboot flash recovery <twrp_img_file_path>
```
### 4) Enter Recovery Mode
* Use the volume up/down buttons to navigate to the "Recovery" option in bootloader. 
* Press power button to select it.

### 5) Wipe all the data
In TWRP, click wipe in the menu, first wipe, then advanced wipe all folders. 

### 6) Prepare ROM file on the phone
Connect your phone to computer, use command
```
adb push <file_path> /sdcard/
```
to upload the aosp, gapps, SuperSU files to your phone.

### 7) Flashing ROM
* Go back to the main menu of TWRP, click install, 
* Should add zip files to the installing queue by following the order: aosp -> SuperSU -> opengapps. 
* Tap install to install the ROM.

### 8) Wipe data again
Click wipe cache/Dalvik option after the installation completes.

### 9) Reboot
Reboot your phone and you should see the modified ROM installed on your phone.

## 2. Install UIWear on your phone and watch

Simply click run in Android Studio and choose the corresponding device, UIWear will automatically installed on your device.
