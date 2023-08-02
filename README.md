# Frida Scripts Repository

<img src="https://frida.re/img/logotype.svg" width="200" alt="Frida Logo">

Welcome to the Frida Scripts Repository! This repository is dedicated to storing and sharing custom scripts developed for use with [Frida](https://frida.re/).

## Script List
### 1. Activity_logger.js
The script is a Frida script for logging and printing information about activity lifecycle events and intents in Android applications. It intercepts and displays details like activity class name, action, data, component, categories, flags, and extras to better understand the flow and data being passed during activity launches and creations.
```yaml
> frida -U -n APP --no-pause -l Activity_logger.js
Activity logger successfully attached.
-------------------------------------------------------------
Starting activity: class com.example.MainActivity
Action: android.intent.action.MAIN
Data: content://com.example.provider/data/12345
Components: com.example/.MainActivity
Categories: [android.intent.category.LAUNCHER, android.intent.category.DEFAULT]
Flags: 335544320 (FLAG_ACTIVITY_NEW_TASK | FLAG_ACTIVITY_CLEAR_TASK | FLAG_RECEIVER_FOREGROUND)
Extras: Bundle[{extra_key=extra_value}]
-------------------------------------------------------------
Starting activity: class com.example.OtherActivity
[...]
```
### 2. File_access_logger.js
The script logs and monitors file access operations in an Android app. It tracks successful and failed file read, write, and delete operations with color-coded messages for easy identification.
```yaml 
> frida -U -n APP --no-pause -l File_access_logger.js
File access logger successfully attached.
-------------------------------------------------------------
SUCCESS     - READ        - [*] file: /data/user/0/com.example.app/files/myfile.txt
SUCCESS     - WRITE       - [*] file: /data/user/0/com.example.app/cache/image.png
FAIL        - READ        - [*] file: /data/user/0/com.example.app/files/sensitive_data.txt
SUCCESS     - DELETE      - [*] file: /data/user/0/com.example.app/cache/temp.txt
[...]
```
## Disclaimer

These scripts are provided as-is and may require modification based on specific use cases. Use them responsibly and ensure you have the necessary permissions to interact with the target applications or processes.
