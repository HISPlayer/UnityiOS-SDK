# XCode Project - Disable Bitcode
After pressing the button **Build** or **Build and Run** on Unity, an XCode project will be created. 

In the case you are facing the following issue:
```
'/Users/hisplayer/Desktop/Test-Builds/iOS-2021/Frameworks/com.my.package/HISPlayer/Plugins/iOS/
HISPlayeriOS.framework/HISPlayeriOS' does not contain bitcode. You must rebuild it with bitcode enabled
(Xcode setting ENABLE_BITCODE), obtain an updated library from the vendor, or disable bitcode for this target.
file '/Users/hisplayer/Desktop/Test-Builds/iOS-2021/Frameworks/com.my.package/HISPlayer/Plugins/iOS/
HISPlayeriOS.framework/HISPlayeriOS' for architecture arm64
``` 

In order to solve this, please go to the **UnityFramework Target > Build Settings**, select **All** option and put the **Build Options > Enable Bitcode**
to **No** as you can see in the following picture

<p align="center">
<img src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/583472e2-9ce0-4b6a-9ad6-616161446328" width=100%>
</p>
