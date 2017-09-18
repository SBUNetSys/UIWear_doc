# UIWear Installation Tutorial

Custom ROM firmware installation

*Before install our modfied ROM, you need to root you Android phone.

1. Download the files: aosp_hammerhead-ota-eng.xujay.zip, BETA-SuperSU-v2.60-20151205163135.zip and twrp-3.1.1-0-hammerhead.img, and get the lateset opengapps apk on http://opengapps.org/. Any package larger than micro is working.

2. Before install the ROM, back up data in your phone. Power off your phone and boot into your phone's bootloader. Hold the power button, two volumn bottons at the same time for about 10 seconds before releasing them. 

3. Use shell command 
fastboot flash recovery <file path>
to flash the TWRP recovery environment to your Android phone.

4. Use the volume down button to scroll to the "Recovery" option in bootloader. Press power button to select it.

5. In TWRP, click wipe in the menu, first wipe, then advanced wipe all folders. 

6. Connect your phone to computer, use command
adb push <file path> /sdcard/
to upload the 3 zip files to your phone.

7. Go back to the main menu of TWRP, click install, add zip file to the queue with the order: aosp, SuperSU, then opengapps. Then click install to install the ROM.

8. You can choose to wipe cache/Dalvik after the installation completes.

9. Reboot your phone and you should see the modified ROM installed on your phone.


Install UIWear on your phone and watch

Simply click run in Android Studio and choose the corresponding device, UIWear will automatically installed on your device.