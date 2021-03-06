# AmazonMobileAutomation

This project is designed to Automate amazon application on Android Mobile using Selenium and TestNG

**Prerequisites:**
1. Java JDK 
2. Appium is installed
3. Android sdk is setup
4. Mobile device is ready for automation run
5. Eclipse is installed 
6. TestNG installed in Eclipse

**Capabilities Added:**
|Capability|Description|Values|
|----|-----------|-------|
|`platformName`|Which mobile OS platform to use|`iOS`, `Android`, or `FirefoxOS`|
|`platformVersion`|Mobile OS version|e.g., `9`, `10`|
|`deviceName`|The kind of mobile device or emulator to use| 'Galaxy S9+' or 'OnePlus6'|
|`udid`|The unquie device id displayed when Android Mobile is connected to System via USB port|'335a4f454f553098'|
|`newCommandTimeout`|How long (in seconds) Appium will wait for a new command from the client before assuming the client quit and ending the session|e.g. `60`|
|`automationName`|Which automation engine to use|`Appium` (default), or `UiAutomator2`|
|`app`|The absolute local path _or_ remote http URL to`.apk` file (Android) or `.apks` file (Android App Bundle), or a `.zip` file containing one of these. Appium will attempt to install this app binary on the appropriate device first. Note that this capability is not required for Android if you specify `appPackage` and `appActivity` capabilities (see below). `UiAutomator2` and `XCUITest` allow to start the session without `app` or `appPackage`. Incompatible with `browserName`. See [here](/docs/en/writing-running-appium/android/android-appbundle.md) about `.apks` file.|`/abs/path/to/my.apk` or `http://myapp.com/app.ipa`|
|`appPackage`| Java package of the Android app you want to run. By default this capability is received from the package manifest (@package attribute value)|`com.example.android.myApp`, `com.android.settings`|
|`appActivity`| Activity name for the Android activity you want to launch from your package. This often needs to be preceded by a `.` (e.g., `.MainActivity` instead of `MainActivity`). By default this capability is received from the package manifest (action: android.intent.action.MAIN , category: android.intent.category.LAUNCHER) |`MainActivity`, `.Settings`|

**Steps to Clone the repository and run test scripts locally:**
1) Navigate to AmazonMobileAutomation repository and , Click on Code and copy the clone Url

![image](https://user-images.githubusercontent.com/46535033/118383097-6576aa00-b5d1-11eb-8ef7-dd729390e2d3.png)

2) Open Eclipse IDE and Switch to GIT repository view, and Click on "Clone Git Repository" Icon

![image](https://user-images.githubusercontent.com/46535033/118383222-4e848780-b5d2-11eb-8aef-b3deb7f2aa36.png)

3) Paste the Git Clone url into URI: field and click on Finish , `More deatil steps on how to add a git repository to Eclispe can be found here` https://github.com/collab-uniba/socialcde4eclipse/wiki/How-to-import-a-GitHub-project-into-Eclipse

![image](https://user-images.githubusercontent.com/46535033/118383275-c94da280-b5d2-11eb-9d0f-a3d9e01df1c3.png)

4) Once the repository is cloned, Right click on Project and Choose 'Import Projects'

5) Now switch to Package Explorer/Project Explorer

6) On Android mobile device, enable developer options and USB debugging option
 
7) Connect the android mobile device to system using usb cable and enter the following command in terminal
`adb devices` , which returns the `uuid` of  connected device

8) Start Appium server on port Number : 4723

![image](https://user-images.githubusercontent.com/46535033/118383473-5c3b0c80-b5d4-11eb-9d36-1b0ad1957c15.png)

9) In Eclipse , open file 'BaseClass.java` and change the following capabilities values according to your android mobile device specifications

  `caps.setCapability(MobileCapabilityType.PLATFORM_NAME,"ANDROID");`
	`caps.setCapability(MobileCapabilityType.PLATFORM_VERSION, "9");`
	`caps.setCapability(MobileCapabilityType.DEVICE_NAME, "Galaxy S9+");`
	`caps.setCapability(MobileCapabilityType.UDID, "335a4f454f553098");`

10) Now navigate to `AmazonTest.java` and Run As 'TestNG Test'



**IMPORTANT FILES**

1) `AmazonMobileAutomation/MobileAutomationProject/Apps` -- This folder contains Android apps that will be tested locally.

2) `AmazonMobileAutomation/MobileAutomationProject/src/test/java/tests/BaseClass.java` -- This class has all the necessary setup and teardown functions.

3) `AmazonMobileAutomation/MobileAutomationProject/src/test/java/tests/AmazonTest.java` -- This class has the script to be run for logging in to the Amazon application and performing the search functionlaity.

4) `AmazonMobileAutomation/MobileAutomationProject/test-output/index.html`-- This file contains the previous run results and is updated after every local run.

5) `AmazonMobileAutomation/MobileAutomationProject/pom.xml`-- This file consists of all the required dependecies for running the Automation framework.

6) `AmazonMobileAutomation/MobileAutomationProject/TestCases.xlsx`- This excel file contains the test sceanrios and test cases for the automated script



