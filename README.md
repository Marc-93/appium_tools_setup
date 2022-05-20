# APPIUM SETUP
One place file explaining all the appium required tools to connect your simulator or physical device to your test framework or just to check the locators with the inspector tool.

## Java
1. Download the last version from java: [download](https://java.com/en/download/manual.jsp).
2. Save java installation path.

## Android Studio

1. Download Android Studio: [download](https://developer.android.com/studio?hl=es&gclid=Cj0KCQjw06OTBhC_ARIsAAU1yOVteCVH_CPYIpdwSqIoV56po1k9sZ__mK6jvASb7kFBb5rC5BB0bKQaAr06EALw_wcB&gclsrc=aw.ds)
2. Clone an Android project or create a new one.
3. Go to Android Studio menu and open `tools/sdk manager`
4. Find the Android Studio sdk path.

## Environment variables

### Windows

1. Open environment variables
2. Add ANDROID_HOME
3. Add JAVA_HOME

![image](img/windows_all_paths.png/windows_android_home.png)
![image](/img/windows_java_home.png)
![image](/img/windows_all_paths.png)

### macOS

1. Download the platform tools package: [download](https://developer.android.com/studio/releases/platform-tools)
2. Unzip the file in your desktop.
3. Open a terminal directly on desktop location.
4. Execute the follwoing command: `$ sudo mv platform-tools /etc`
5. Execute the following command to add platform-tools to path: `$ sudo vim /etc/paths`
6. Type `i` to edit.
7. Add `/etc/platform-tools`.
8. Save file typing `:q!`.
9. Restart the terminal.

## Create Android emulator

1. Open Android Studio.
2. Open `adv manager`.
3. Click `Create Virtual Device`.
4. Select the device, go to next screen.
5. Install last API version, go to next screen.
6. Show advanced options, change the graphics to hardware option and click finish.
7. Now you have the virtual device available.

## ADB

10. To get the device id: `adb devices`
11. To get the main activity, execute the command: `adb shell dumpsys window | grep -E 'mCurrentFocus'`

## Xcode

1. Download xcode from AppStore

## UICatalog

1. Clone the [UICatalog](https://github.com/appium/ios-uicatalog) repository from github.
2. Open the folder project.
3. Go to UICatalog folder.
4. Open the UICatalog.xcodeproj file with Xcode.
5. Select the iphone device.
6. Click on run button.

## Nodejs

Install node using terminal: `$ brew install node.js`

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

## Connect Android

1. Click on "Edit configurations"
     - Set the ANDROID_HOME path: `your_android_home_sdk_path`
     - Set the JAVA_HOME path: `your_java_path`
     - Restart appium
2. Start the Appium server
3. Open the Appium inspector:
     - Set host: `127.0.0.1`
     - Set remote port: `4723`
     - Set remote path: `/wd/hub/`
     - Set capabilities:
`
{
  "platformName": "android",
  "automationName": "UiAutomator2",
  "appPackage": your_app_package,
  "appActivity": your_app_activity"
}
`
4. Start appium inspector session.


## Connect iOS

1. Click on start server.
2. Open the Appium inspector:
     - Set host: `127.0.0.1`
     - Set remote port: `4723`
     - Set remote path: `/wd/hub/`
     - Set capabilities:
`
{
"platformName": "iOS",
"automationName": "XCUITest",
"deviceName": device,
"app": app_path
}
`
3. Start appium inspector session.
