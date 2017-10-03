# UIWear Installation Tutorial

## 1. Flash Custom Android AOSP ROM on Nexus 5

**WARNING: Please backup your data before flashing the phone.

### 0) Prerequisites
* **Make sure you have a backup of your Nexus 5 data**
* Ensure you have USB Debugging enabled on your Nexus 5.
* Make sure you have installed Android tools on your PC, i.e., adb, fastboot.
* Unlock the Nexus 5 by following these steps: https://www.androidpit.com/how-to-unlock-nexus-5-bootloader.

### 1) Download ROM files: 

*  **aosp_hammerhead-ota-eng.xujay.zip**: This is our customized ROM which enhances the functionalities of Accessibility mechanism.

*  **BETA-SuperSU-v2.60-20151205163135.zip**: For rooting the phone.

*  **twrp-3.1.1-0-hammerhead.img**: https://dl.twrp.me/hammerhead/twrp-3.1.1-0-hammerhead.img.html

*  Google apps: at http://opengapps.org/. 

### 2) Entering Bootloader mode
* Power off your phone.
* Hold the power button, volume up, volume down bottons simultaneously for around 10 seconds.
* After then, the phone will reboot into bootloader mode.

### 3) Flashing Recovery Environment

Flashing the TWRP recovery environment to your Android phone by using command:
```
fastboot flash recovery <twrp_img_file_path>
```

### 4) Enter Recovery Mode
* Use the volume up/down buttons to navigate to the "Recovery" option in bootloader. 
* Press power button to select it.

### 5) Wipe all the data
In TWRP, click wipe in the menu, first wipe, then advanced wipe all folders. 

### 6) Prepare ROM file on the phone
Connect your phone to computer, use the command below to upload the aosp, gapps, SuperSU files to your phone.
```
adb push <file_path> /sdcard/
```

### 7) Flashing ROM
* Go back to the main menu of TWRP, click install.
* Should add zip files to the installing queue by following the order: aosp -> SuperSU -> opengapps. 
* Tap install to install the ROM.

### 8) Wipe data again
Click wipe cache/Dalvik option after the installation completes.

### 9) Reboot
Reboot your phone and you should see the modified ROM installed on your phone. The first time to boot might take a while, please be patient.

## 2. Install UIWear on your phone and watch

Simply click run in Android Studio and choose the corresponding device, UIWear will automatically installed on your devices.

## 3. Configure UIWear - phone side

### 1) Open service
Open the UIWear App, first click "Start Proxy", it will automatically jumps to Accessibility in Settings, Under Services, choose UIWear Accessibility Services, turn it on.

### 2) Choose Apps
In "Select App", choose the apps you want to use with UIWear.

### 3) Upload preference files
* Each app has its corresponding preference files. 
* They are necessary for the connection between phone and watch. Use the following command to upload these files.
```
adb push <preference_file_path> /sdcard/UIWear/<app_domain>/Preferences
```

### 4) Allow cache
Turn on Cache Status to achieve full use of UIWear.

## 4. Configure UIWear - watch side

### 1) Open service
Open the UIWearProxy App, click "Start WearProxy" and exit.

### 2) Install corresponding apks
* Each phone app need an compainon watch app pre-installed on the watch to let the proxy work. 
* Use the following command to install watch apks on your watch.
```
adb install <apk_file_path>
```

### 3) Set connection
When it is the first use, phone app must start first to set connection between phone and watch.

## X. Troubleshooting

### 1) I cannot enter Recovery Mode after choosing "Recovery" option in bootloader. 
* Make sure you flash the TWRP recovery environment properly in the previous step.
* If the phone starts an infinite reboot loop, try to enter the bootloader mode again when the phone is off and flash TWRP recovery environment again.

### 2) I cannot install the zip files / I get error during installing zip files.
* Check if the zip files is properly trasferred in the previous step.
* If you choose a large version of gapps and get the error message of insufficient storage, try a smaller version of gapps.

### 3) I get error message after rebooting, which says "Google play service stops". / I cannot login in Play Store. / I cannot successfully pair my phone and watch. / The connection between my phone and watch is not stable.
* Go to Setting-Apps, choose Google and Google Play and force stop them, try again after several hours.
* Watch pairing need Google play service works. Try the method above and pair your watch again.




