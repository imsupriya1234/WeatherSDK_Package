# WeatherSDK_Package
Unity package for weather.

# Unity WeatherSDK package

This repository is a working WeatherSDK package that demonstrates:
- A Unity package folder with a GameObject bridge that shows platform-native Toast message for Android or UIAlert for iOS.
- A Weather scene uses WeatherUI scripts to get device Location from the LocationService script and call the WeatherAPI to fetch temperature.
- Android and iOS native plugin templates to show native UI.
- Instructions to create and export the Unity package/prefab.

**Note:**
To use in Unity, import the folder as a copy inside `Assets/` as `WeatherSDK/` into an existing Unity project (Unity 2020.3+ recommended). [used Unity 6000.51f1 LTS]

## Scene Setup

- 1. 
Check the Weather scene, how the Toast Button functionality has been used.

- 2.
>> Create a new scene.
>> Add a Button in the canvas. Attach the NativeBridge script to the Button.
>> Create a GameObject Attach - WeatherUI script.
   Reference the LocationService, WeatherAPI scripts, and Button component.
>> Create a GameObject Attach - LocationService script.
>> Create a GameObject Attach - WeatherAPI script.

- 3.
For the Android plugin, the Java file is placed under `WeatherSDK/Plugins/Android/...` and will be compiled into the Android package when building.

For the iOS plugin, the Objective-C++ file is under `WeatherSDK/Plugins/iOS/...`. When building for iOS, 
Xcode will compile this file, and you may need to add the `-ObjC` linker flag depending on the Unity version.

- 4.
To make Android Build -
>> Generate a Manifest file from Unity Project settings.
   Then add Internet and Location permission inside the Manifest file.
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />`
`<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />`

To make iOS Build -
>> Export the iOS project.
>> Open in Xcode.
>> Give Internet and Location permission.

Run in the Editor: Toast falls back to `Debug.Log`. On the device, native UI will show.

- 5. [BUILD]
