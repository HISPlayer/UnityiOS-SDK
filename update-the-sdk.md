# Update the SDK

Through this guide, you will be introduced how to update the SDK if you already have installed the SDK previously.

## Remove Old Package

Remove the previous HISPlayer Android / iOS SDK package from Unity Package Manager

**Window > Package Manager > Packages - HISPlayer > HISPlayer Android IOS SDK > Remove**

<p align="center">
<img width="700" src="./assets/remove-package.PNG">
</p>

<br>

## Import New package

Importing the new package is the same as importing other normal packages in Unity. 
Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package >  HISPlayerSDK_Android_iOS unity package**


<p align="center">
<img width="450" src="./assets/import-package.png">
</p>

<br>

## Configure Unity for iOS
Open the window **Tools > HISPlayer** located in the upper side of the screen > Click on Player Settings Configuration > Select Build Target to iOS > Set all the required settings.

<p align="center">
<img width=75% alt="image" src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/f0cdaf97-a01e-45f3-92d4-291d5e1f5ceb">
</p>

<p align="center">
<img width=40% alt="image" src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/cf52dda7-cbc8-49cd-b808-c51ba35752ff">
<img src="./assets/embedded-bin.png" width=40%>
</p>


## Update License Key
Input the license key that is associated with the SDK through HISPlayer properties. If the license key is not valid, the player won't work and will throw an error message.

<p align="center">
<img width="400" src="./assets/license-key.PNG">
</p>
