# android-reverse-engineering-resources

# Tools

**Open source apk decompiler**
- https://github.com/skylot/jadx

**Paid apk decompiler with debugger**
- https://www.pnfsoftware.com/jeb/

**Tools i want to test**
- https://codeshare.frida.re/
  - https://infosecwriteups.com/hail-frida-the-universal-ssl-pinning-bypass-for-android-e9e1d733d29 
- https://github.com/NotSoSecure/android_application_analyzer
- https://github.com/MobSF/Mobile-Security-Framework-MobSF

**Bypassing android ssl pinning**
- https://blog.netspi.com/four-ways-bypass-android-ssl-verification-certificate-pinning/

**Data transformation/crypto stuff**
- https://gchq.github.io/CyberChef/
- Clojure REPL + https://github.com/funcool/buddy

**Root physycal android device**
- Search device model here: https://forum.xda-developers.com/

# Notes
## Signing a jar
https://stackoverflow.com/questions/31911149/adb-install-parse-failed-unexpected-exception

Getting invalid sha1 error after signing:
https://stackoverflow.com/questions/8176166/invalid-sha1-signature-file-digest

## ADB

### Start and stop app via adb
`adb shell am start com.my.app/<activity>`

`adb shell am force-stop com.my.app.package`

**Start app activity and wait for debugger attach**
`adb shell am start -D -S -n com.my.app/<activity>`

### Get android_id from device with adb 
https://stackoverflow.com/questions/56577931/how-to-find-android-id-from-device-not-programmatically

**Get & Set (Android <= 7)**

`adb shell settings get secure android_id`

`adb shell settings put secure android_id <android_id>`

### Get app logs
`adb logcat com.my.app`

### Find local db files from app
On a rooted android:
```shell
adb shell
cd /data/data/com.my.app/databases
```
