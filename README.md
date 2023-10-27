# Mac OS: Adding installation path

Setup for adding installation paths for CMD tools in Mac OS

## 1. Download the required zip / folders for the tool

E.g. Android Debug Bridge (ADB):

**Android Debug Bridge**: ADB stands for Android Debug Bridge. It is a versatile command-line tool that comes with the Android SDK (Software Development Kit). ADB allows developers to communicate with and control Android devices, such as smartphones and tablets, from a computer. It is commonly used for various tasks, including:

Installing and uninstalling apps on Android devices.
Pushing and pulling files between a computer and an Android device.
Debugging and diagnosing issues on Android devices.
Running shell commands on an Android device.
Managing device emulators.
Accessing system logs and device information.
Developers often use ADB to test and debug their Android applications during development, but it can also be useful for advanced users and enthusiasts who want to customize or troubleshoot their Android devices.

To use ADB, you need to have the Android SDK installed on your computer, and you'll also need to enable Developer Options and USB Debugging on your Android device. Once configured, you can connect your device to your computer and use ADB commands to interact with it.

The ADB toolset can be downloaded here: <a href="https://developer.android.com/tools/releases/platform-tools">https://developer.android.com/tools/releases/platform-tools</a>

## 2. Update the installation directory mapping for the tool ( /etc/paths)
Once the toolset is download, extract the zip and copy the folder location in `/etc/paths` . E.g. folder location can be `/Users/testuser/coding/installed/adb/platform-tools`

Directly running the **adb** command after extraction won't work. 
```
$ adb devices
zsh: command not found: adb
```
The **/etc/paths** contains the installation folders for CMD tools. Open the file using `vi` editor and add the folder location.
```
sudo vi /etc/paths
```
Example snapshot of /etc/paths after adding the location would be: 
```
/usr/local/bin
/usr/bin
...
/Users/testuser/coding/installed/gradle
/Users/testuser/coding/installed/maven
...
/Users/testuser/coding/installed/adb/platform-tools <----- ( Folder location )
...
```

## 3. Save the paths file and restart
(press ESC then :wq ) to save the changes. On restarting the terminal, the `adb` command would start to work.

```
$ adb devices

List of devices attached
emulator-5554	device

```

