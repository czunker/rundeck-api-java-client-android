rundeck-api-java-client-android
===============================

This is a fork of https://github.com/vbehar/rundeck-api-java-client.
I needed this lib for my experimental Rundeck Android client, but Android doesn't support a current version of Apache HTTP Client used by this lib:
http://android-developers.blogspot.de/2011/09/androids-http-clients.html

When using the Rundeck Java API with a HTTP Client jar from Apache, you'll get the error message:
NoSuchMethodException SSLFactory.init

I'm not the first one having this problem. I found a project from Dirk Boye:
http://code.google.com/p/httpclientandroidlib/
His project repackages the Apache HTTP Client for Android.
For more details see his project page or this stackoverflow question:
http://stackoverflow.com/questions/4799151/apache-http-client-or-urlconnection

So I cloned the Rundeck Java API and replaced all occurences of org.apache.http with ch.boye.httpclientandroidlib and added the httpclientandroidlib as dependency to maven pom.xml. 
After that I repacked the jar, put it in my android app, recompiled it and everything worked fine.