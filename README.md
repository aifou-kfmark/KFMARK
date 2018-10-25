# KFMark made by FView

Please note that this app is in early stages of development. Although we plan to release KFMark as a free app on Google Play, this is still very much a commercial project, thus no plan for open-sourcing is disclosed as of now. FView Technology owns the rights to this app and any unlicensed modification, distribution or reverse-engineering is strictly prohibited.

## Get up and running

Please download BOTH of the following files on the [Release page](https://github.com/Septillion/KFMark/releases).

- KFMark APK
- KFMark PC Assistant

After installing the base APK on your phone, you have to enable the `Developer Mode` on your phone (please search online for how to do that on your model) and enable `USB Debugging`. Then connect your phone to a Windows PC and use KFMark PC Assistant to activate the background `daemon` used to measure FPS and other factors. Every time you restart your device, you have to run KFMark PC Assistant again. 

For Mac and Linux users, please download only the KFMark APK and `KFMark daemon` (with adb bundled). Unzip this file and manually run the following commands using Terminal in the unzipped directory:

	./adb push ./daemon/daemon /data/local/tmp
	./adb shell chmod 777 /data/local/tmp/daemon
	./adb shell "./data/local/tmp/daemon &"

## Feature

KFMark V1.0 would allow you to profile and benchmark 3D games running on Android, and show current FPS on a floating window, giving you direct indication of how smooth the game is running on your device.

You can optionally record a gaming session and get a complete history of FPS, CPU Frequency and Battery Drain.

All of the benchmarking history is stored locally on your phone for you to review.

KFMark is compatible with Android 6 and up.

## Release Note

2018-10-30
Version 1.0
Initial version.

## Privacy

KFMark runs locally on your devices and requires only storage permissions. All of your benchmarking data is stored locally on your phone and is not uploaded to any server.

## Bug Report

Please go to the Issue page to submit a bug report. Please first search for your bug and see if anyone has already submitted the same bug. 

When submitting a bug, please follow the pattern:

	Device Model:
	Device Android Version:
	Device ROM Version:
	---
	Bug Description:
	---
	Steps to Reproduce:
