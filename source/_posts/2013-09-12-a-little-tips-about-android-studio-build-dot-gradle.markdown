---
layout: post
title: "A little tips about android studio build.gradle"
date: 2013-09-12 14:45
comments: true
categories: Android gradle NDK
---

As far as we know,<s> Android stuido doesn't support.so libraries yet</s>.but we may have some project need to use it.Googleing around for it.i found it and put it on my Gist.here it is.
<br>
{% gist 6533747 %}
<br>
Most people like me will release the apk file frequently.but how do we exactly know which version we are using.<u>we may have the same version code and version name but one was release on morning and bug still exist ,another was at night but bug was fixed it.</u>the traditional way was rename it when release.but a lazy way was let the machine do it.just using a little groovy script.when we exectue asselbleRelease task.the final apk file will automatically rename to APPNAME-VERSION-DATE.apk or the other type you want.
<br>
{% gist 6533922 %}
<br>

and more will continue post below ....

