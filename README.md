# Pogo-Account-Checker
## Information
Pogo Account Checker is an Android app that checks if Pokémon Go PTC accounts are banned or not. It does so by using the Pokémon Go app, no third party APIs are used.
* [Discord](https://discord.gg/sNv8sPr "Discord") - For support
## Requirements
* Rooted Android device with Android 5.0 or higher, that's all
## Setup
### Rooting
1. Ensure your phone has an unlocked bootloader and is able to support root. [LineageOS](https://lineageos.org/ "LineageOS") is a good place to start for a custom ROM and they have good installation instruction for each device.
2. Install [Magisk](https://www.xda-developers.com/how-to-install-magisk/ "Magisk") to root the phone via recovery. Repackage the MagiskManager App and add Pokémon Go to Magisk Hide. Make sure to delete the folder `/sdcard/MagiskManager` after repackaging. It's necessary to pass the Safetynet check to run Pokémon Go on rooted phones. Check the Safetynet status in the MagiskManager App.
### APK
You can get the APK by directly downloading it from Github (`apk/pogo-account-checker.apk`), or by building it yourself. You will have to take some additional steps if you want to build the APK yourself:
1. Install the latest version of [Android Studio](https://developer.android.com/studio/ "Android Studio").
2. `git clone` and open the project in Android Studio.
3. The application uses the [ML Kit's text recognition APIs](https://firebase.google.com/docs/ml-kit/recognize-text "ML Kit's text recognition APIs"). In order for the text recognition to work a `google-services.json` file must be downloaded and placed in the `app` folder. This file contains confidential information, hence it's not added to this repo. [Here](https://firebase.google.com/docs/android/setup "How to get google-services.json") is explained how to obtain this file.
4. Install the app on your phone by clicking the green play button in Android Studio.
## Checking accounts
First you have to put your PTC accounts in a `.txt` file, username and password should be seperated by a comma. TXT file example:
```txt
username01,password01
username02,password02
```
Then transfer the file to your phone. Next open the app and select the file. Press start to start checking the accounts. The checked accounts can be found in the `PogoAccountChecker` folder on your phone. In this folder there will be a maximum of four files:
* `not_banned.txt` - contains accounts that still work
* `banned.txt` - contains accounts that are banned
* `not_exist` - contains accounts that don't exist or have an incorrect username/password
* `error.txt` - contains accounts for which checking failed 10 times in a row, this can for example happen when there is no internet connection
