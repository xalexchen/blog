---
layout: post
title: "Android ADB tricks"
date: 2014-02-28 12:33:34 +0800
comments: true
categories: Android Tricks
---
With android adb tools.we can reboot cell phone.push/pull data from/into device.analyzing app performance etc. but i am not going to talk about this.because i am going to give you a really cool way to master the android adb tools or adb shell.  
<br>
###Wake up phone on a hacker way



Almost both android developer will keep connected our phone to the PC.as we all konw to wake up the phone we need to push the power button.come on.we're lazy and geek guy.can we act it like a programer ? like on the movie some guy just type in a command ? Open your terminal and input the following code. 
```
adb shell input keyevent 26

```
the priciple was we make a fake power button event and report to android event system.for more keycode value please reference the following [link](http://stackoverflow.com/questions/7789826/adb-shell-input-events)

`More: increate/decrease sound volume`
  
<br>
###Launch app on a geek way



What if you want to open Camera app without touch your phone.it can be done ? definitely..

```
adb shell am start -n com.android.camera/com.android.camera.Camera

```
okey,you want to make a call?.

```
am start -a android.intent.action.CALL -d tel:10086

```

`Note:any other app can be done if your know the exactly package name and Activity component name. `

<br>
### Protect your privacy



   your friends need to borrow your phone for a while.you don't want him open your Gmail or WeChat to see anythings.(maybe your GF or BF (￣▽￣)") anyway.your can't just directly tell them.but we can do it on a silence way.just let it disappear on the screen.it's not to delete your app.more safely(#need root premission#)

```
adb shell 
su
pm disable com.google.android.gm
// roll it back when your need
pm enable com.google.android.gm

```   
`Note:you can do it on any app if you know the exactly package name.`
