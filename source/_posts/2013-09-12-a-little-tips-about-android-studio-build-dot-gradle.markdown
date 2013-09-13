---
layout: post
title: "A little tips about android studio build.gradle"
date: 2013-09-12 14:45
comments: true
categories: Android gradle NDK
---

1.As far as we know,<s> Android stuido doesn't support.so libraries yet</s>.but we may have some project need to use it.Googleing around for it.i found it and put it on my Gist.here it is.
<br>
{% gist 6533747 %}
<br>
2.Most people like me will release the apk file frequently.but how do we exactly know which version we are using.<u>we may have the same version code and version name but one was release on morning and bug still exist ,another was at night but bug was fixed it.</u>the traditional way was rename it when release.but a lazy way was let the machine do it.just using a little groovy script.when we exectue asselbleRelease task.the final apk file will automatically rename to APPNAME-VERSION-DATE.apk or the other type you want.
<br>
{% gist 6533922 %}
<br>

3.When we try to build a simplest gradle call (e.g clean or assembleRelease) is pretty slow.On my computer it took around eight seconds for clean task.if you tell gradle to use a daemon to build.just create a file named gradle.properties in the following directory:
	/home/<username>/.gradle(linux)
	/Users/<username>/.gradle(Mac)
	C:\Users\<username>\.gradle\(Windows)
Add this line to the file:
	org.gradle.daemon=true

From know on Gradle will use a daemon to build,whetehr you are using gradle from command line or building in android studio.add this files means the daemon won't stop automatically even you don't build anything with gradle for sometime.
so the daemon alway ready to go and no need to a long start-up time at the next build.share by TIME ROSE <a href="https://www.timroes.de/2013/09/12/speed-up-gradle/">HOW TO… SPEED UP GRADLE BUILD TIME</a>
<br>
and more will continue post below ....

