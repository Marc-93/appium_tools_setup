# APPIUM SETUP
One place file explaining all the appium required tools to connect your simulator or physical device to your test framework or just to check the locators with the inspector tool.

## Java
1. Download the last version from java: [download](https://java.com/en/download/manual.jsp).
2. Save java installation path, into your environment variables `$JAVA_PATH`

## Android Studio

1. Download Android Studio: [download](https://developer.android.com/studio?hl=es&gclid=Cj0KCQjw06OTBhC_ARIsAAU1yOVteCVH_CPYIpdwSqIoV56po1k9sZ__mK6jvASb7kFBb5rC5BB0bKQaAr06EALw_wcB&gclsrc=aw.ds)
2. Clone an Android project or create a new one.
3. Go to Android Studio menu and open `tools/sdk manager`
4. Find the Android Studio sdk path `/users/{user}/Library/Android/sdk`.

## Environment variables


## Create Android emulator

1. Open Android Studio.
2. Open `adv manager`.
3. Click `Create Virtual Device`.
4. Select the device, go to next screen.
5. Install last API version, go to next screen.
6. Show advanced options, change the graphics to hardware option and click finish.
7. Now you have the virtual device available.

## ADB

1. Download the platform tools package: [download](https://developer.android.com/studio/releases/platform-tools)
2. Unzip the file in your desktop.
3. Open a terminal directly on desktop location.
4. Execute the follwoing command: `$ sudo mv platform-tools /etc`
5. Execute the following command to add platform-tools to path: `$ sudo vim /etc/paths`
6. Type `i` to edit.
7. Add `etc/platform-tools`.
8. Type  `:q!`.
9. Restart the terminal.
10. To get the device id: `adb devices`
11. To get the main activity, execute the command: `adb shell dumpsys window | grep -E 'mCurrentFocus'`

## Xcode

1. Download xcode from AppStore
2. Clone the [UICatalog](https://github.com/appium/ios-uicatalog) repository from github.
   1. Open the folder project.
   2. Go to UICatalog folder.
   3. Open the UICatalog.xcodeproj file with Xcode.
   4. Select the iphone device.
   5. Click on run button.
   6. The emulator for device selected will be generated.

## Nodejs

Install node through terminal: `$ brew install node.js`

## Appium

1. Install appium through terminal: `$ npm install -g appium`
     - Try with sudo if there are errors: `$ sudo npm install -g appium`
2. Install wd through terminal: `$ npm install wd`
3. Link for Appium Desktop version: [download](https://github.com/appium/appium-desktop/releases) 
4. Execute this command to sign appium version: `codesign --deep --sign - /Applications/Appium\ Server\ GUI.app`
5. Download Appium inspector: [download](https://github.com/appium/appium-inspector/releases)
6. Try to open Appium apps
     - If there are some issues, go to 'preferences/security/general'
     - Click to allow appium.
7. Click on "Edit configurations"
     - Set the ANDROID_HOME path: `/users/{user}/Library/Android/sdk`
     - Set the JAVA_HOME path: `/usr/libexec`
     - Restart appium
     - Start the server
8. Open the Appium inspector:
     - Set host: `127.0.0.1`
     - Set remote port: `4723`
     - Set remote path: `/wd/hub/`
     - Set capabilities: 

`
{
  "platformName": "android",
  "appium:automationName": "UiAutomator2",
  "appium:appPackage": "cash.sherwood",
  "appium:appActivity": "cash.sherwood.ui.main.MainActivity"
}
`
