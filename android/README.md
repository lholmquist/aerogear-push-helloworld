# helloworld-push-android: Basic Mobile Application showing the AeroGear Push feature on Android

Author: Daniel Passos (dpassos)
Level: Beginner
Technologies: Java, Android
Summary: A basic example of Push : Registration and receiving messages.
Target Product: Mobile
Product Versions: EAP 6.1, EAP 6.2, EAP 6.3
Source: https://github.com/aerogear/aerogear-push-helloworld/android

## What is it?

This project is a very simple helloworld, to show how to get started with the UnifiedPush Server on Android.

## System requirements

* [Java 7](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
* [Maven 3.1.1](http://maven.apache.org)
* Latest [Android SDK](https://developer.android.com/sdk/index.html) and [Plataform version](http://developer.android.com/tools/revisions/platforms.html)
* Latest [Android Support Library](http://developer.android.com/tools/support-library/index.html) and [Google Play Services](http://developer.android.com/google/play-services/index.html)
* Latest [Maven Android SDK Deployer](https://github.com/mosabua/maven-android-sdk-deployer)

## Configure

* Have created a variant in UnifiedPush admin console
* Have a device (push notification not available on simulator)

## Build and Deploy the HelloWorld


### Change Push Configurations

In android/src/org/jboss/aerogear/unifiedpush/helloworld/Constants.java find replace UPS URL, variant, secret and gcm sender id:

```
String UNIFIED_PUSH_URL = "";
String VARIANT_ID = "";
String SECRET = "";
String GCM_SENDER_ID = "";
```

## Application Flow

### Registration

Explain quickly the registration flow + screenshot of the console where we can check in the Installation page if the device is registered

### Sending Push Notification

* Showing the compose message feature

* Maybe also the CURL ?


## FAQ

### Build dependencies locally

Google doesn't ship all the needed libraries to maven central. You need locally deploy them using the [maven-android-sdk-deployer](https://github.com/mosabua/maven-android-sdk-deployer).

#### Checkout maven-android-sdk-deployer
```
git clone git://github.com/mosabua/maven-android-sdk-deployer.git
```

#### Install android platform
```
cd $PWD/maven-android-sdk-deployer/platforms/android-19
mvn install -N --quiet
```

#### Install google-play-services
```
cd $PWD/maven-android-sdk-deployer/extras/google-play-services
mvn  install -N --quiet
```

#### Install compatibility-v4
```
cd $PWD/maven-android-sdk-deployer/extras/compatibility-v4
mvn install -N --quiet
```

#### Install compatibility-v7-appcompat
```
cd $PWD/maven-android-sdk-deployer/extras/compatibility-v7-appcompat
mvn install -N --quiet
```


## Debug the Application

```
mvn clean package android:deploy android:run
```
