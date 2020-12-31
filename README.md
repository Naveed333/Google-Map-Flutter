# This project is only for Google Map Flutter and use of package "google_maps_flutter"

following steps are required

step 1 :  Install dependencie of name "google_maps_flutter"

step 2 : Getting an API key for both Android and iOS. For Android, follow the instructions at https://developers.google.com/maps/documentation/android-sdk/get-api-key — Get API Key.


step 3 : Add your API key to your Flutter app in the application manifest    (android/app/src/main/AndroidManifest.xml)  this is for android

 <meta-data android:name="com.google.android.geo.API_KEY"
               android:value="YOUR ANDROID API KEY HERE"/>


step 4 : Add your API key to your Flutter app in the application delegate (ios/Runner/AppDelegate.swift) this is for IOS

import UIKit
import Flutter
import GoogleMaps

@UIApplicationMain
@objc class AppDelegate: FlutterAppDelegate {
  override func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
  ) -> Bool {
    GMSServices.provideAPIKey("YOUR KEY HERE")
    GeneratedPluginRegistrant.register(with: self)
    return super.application(application, didFinishLaunchingWithOptions: launchOptions)
  }
}



===============================================================================================================

If Case of Error comes in Android

step 1 : path("android/app/build.gradle") add 

  defaultConfig {...
  
        multiDexEnabled true
    }
    
    
dependencies {...
    implementation 'androidx.multidex:multidex:2.0.1'
}


If Still Error Come 

step 2 : path("android/gradle.properties) add

...
android.enableDexingArtifactTransform=false






