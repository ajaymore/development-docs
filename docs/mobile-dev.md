- [iOS](#ios)
- [Android](#android)

## iOS

**1. Development setup | Project creation**
```
react-native init myapp
cd myapp/ios
pod init | update pod file with relevant details
pod install | Open workspace in xcode, start packager from terminal
Update app name, bundle identifier in general tab
Run project from xcode
Edit code in VSCode
```

**2. Code development | IDEs Text Editor**
  - Xcode
    - Project Clean CMD + Option + SHIFT + K
  - VSCode

**3. Third party component integration (iOS, Android)**
```
# react-native-firebase
yarn add react-native-firebase
react-native link react-native-firebase
update podfile
cd ios && pod update
update AppDelegate.m file
Create firebase project, download GoogleService-Info.plist
add GoogleService-Info.plist to root of the project
To add libraries -> Libraries ➜ Add Files to [your project's name]
Update URL Schemes in Info
```
```
# react-native-google-signin
```
**4. Push notifications**

**5. Reusable Component library**
  - Form wrappers
  - Data fetching logic
  - File upload logic

**6. App Signing | Certificate management**
  - Choose automatic signing in XCode
  - Create App Id at https://developer.apple.com/account/ under Certificates, Identifiers & Profiles
  - Create Push notification key under Keys if required
  - Create App in http://itunesconnect.apple.com/
  - Update relevant url schemes under Info section in Xcode

**7. Building & Testing deployments**
  - Add beta testers under Users & Roles at http://itunesconnect.apple.com/
  - Create 1024*1024 Icon, use icon Set Generator utility to generate assets
  - Product -> Scheme -> Edit Scheme -> Run | choose debug or release
  - comment/uncomment packaging code AppDelegate.m
  - Info.plist -> App Transport Security Settings -> Exception Domains -> localhost -> NESException -> YES | NO
  - Product > Archive > Window > Organizer > Validate > Upload

**8. Using emulators**
  - Optimize Rendering for window size is disabled
  - Use http://localhost to access local network

**9. App submission guides**
  - Verify permissions
```
<key>NSCameraUsageDescription</key>
<string>$(PRODUCT_NAME)  would like to use your camera to capture pictures of your field trip and submit them in Field Trip report.</string>
<key>NSLocationAlwaysUsageDescription</key>
<string>We may need your location information to establish direct communication</string>
<key>NSLocationWhenInUseUsageDescription</key>
<string>We may need your location information to establish direct communication</string>
<key>NSMicrophoneUsageDescription</key>
<string>$(PRODUCT_NAME) would like to use you microphone to capture sound while you are recording your videos for the act of active citizenship report</string>
<key>NSPhotoLibraryAddUsageDescription</key>
<string>$(PRODUCT_NAME) would like to save photos to your photo gallery. These are the photos that you may want to download from the app for viewing and editing with your phone.</string>
<key>NSPhotoLibraryUsageDescription</key>
<string>$(PRODUCT_NAME) App would like to access your photo gallery for you to upload photos with the field reports. None of your photos would be accessed without your permission.</string>
```
  - Description
  - [SplashScreen Library](https://github.com/crazycodeboy/react-native-splash-screen)
    [SplashScreen Setup](https://medium.com/handlebar-labs/how-to-add-a-splash-screen-to-a-react-native-app-ios-and-android-30a3cec835ae)

**10. App Deployment**
  - Toggle step 6 & 8



## Android

**1. Development setup | Project creation**
```
react-native init rnative
Open in Android
Change package name app/build.gradle, MainApplication.java, AndroidManifest.xml, Strings.xml
Add Firebase
Edit code in VSCode
```

**. Deep Linking

https://www.raywenderlich.com/6080-universal-links-make-the-connection
https://developer.apple.com/library/archive/documentation/General/Conceptual/AppSearch/UniversalLinks.html#//apple_ref/doc/uid/TP40016308-CH12-SW2
https://medium.com/@parkerdan/react-native-universal-linking-ios-deep-linking-android-with-a-rails-server-d993649ae6be
https://developer.android.com/training/app-links/deep-linking
```
adb shell am start -W -a android.intent.action.VIEW -d "mychat://mychat/chat/Eric" com.simpleapp
xcrun simctl openurl booted mychat://chat/Eric
```

**2. Code development | IDEs Text Editor**
  - Android Studio
    - Format > Option | CMD + L
  - VSCode

**3. Third party component integration (iOS, Android)**
```
# react-native-firebase
firebase is connected in android studio

repositories {
      google()
      jcenter()
  }
  dependencies {
      classpath 'com.android.tools.build:gradle:3.1.3'
      classpath 'com.google.gms:google-services:4.0.1'
      // NOTE: Do not place your application dependencies here; they belong
      // in the individual module build.gradle files
  }

allprojects {
    repositories {
        mavenLocal()
        google()
        jcenter()
        maven {
            // All of React Native (JS, Obj-C sources, Android binaries) is installed from npm
            url "$rootDir/../node_modules/react-native/android"
        }
    }
}

Add latest firebase and play-services libraries
update all installed packages from compile to implementation
Update MainApplication.java

Update react-native-vector-icons to 
compileOnly "com.facebook.react:react-native:${safeExtGet('reactNativeVersion', '+')}"
```
```
# react-native-google-signin
Enable google login in firebase
yarn add react-native-google-signin
react-native link react-native-google-signin
latest of implementation 'com.google.android.gms:play-services-auth:15.0.0'
```

**4. Push notifications**
https://github.com/OneSignal/OneSignal-Gradle-Plugin/issues/37#issuecomment-391983620
https://rnfirebase.io/docs/v4.3.x/messaging/android
https://rnfirebase.io/docs/v4.3.x/notifications/android

**5. Reusable Component library**
  - Form wrappers
  - Data fetching logic
  - File upload logic

**6. App Signing | Certificate management**
  - [Create keystore, add SHA1 to firebase app](https://flutter.io/android-release/)
```
# debug sha1
keytool -exportcert -list -v -alias androiddebugkey -keystore ~/.android/debug.keystore
# production sha1
keytool -genkey -v -keystore ~/keys/mobileapp/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias mobileapp
keytool -exportcert -list -v -alias mobileapp -keystore ~/keys/mobileapp/key.jks
```

**7. Building & Testing deployments**
  - https://play.google.com/apps/publish

**8. Using emulators**
  - 

**9. App submission guides**
  - Description
  - [SplashScreen Library](https://github.com/crazycodeboy/react-native-splash-screen)
    [SplashScreen Setup](https://medium.com/handlebar-labs/how-to-add-a-splash-screen-to-a-react-native-app-ios-and-android-30a3cec835ae)
```
create a 1242 X 2436 asset and export from XD
```

**10. App Deployment**
  - Toggle step 6 & 8


## Miscellaneous

- React Art, d3
  - https://medium.com/@jennysihua/creating-a-donut-chart-in-react-native-with-d3-and-art-2a7ac91dda5c
  - https://stackoverflow.com/questions/37658957/no-component-found-for-view-with-name-artshape
  - https://medium.com/the-react-native-log/animated-charts-in-react-native-using-d3-and-art-21cd9ccf6c58
