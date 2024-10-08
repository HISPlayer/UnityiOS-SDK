# Update the SDK

Through this guide, you will be introduced how to update the SDK if you already have installed the SDK previously. Please, restart the Editor before continuing.

## Remove Old Package

Remove the previous HISPlayer SDK package from Unity Package Manager.

**Window > Package Manager > Packages - HISPlayer > HISPlayer SDK > Remove**

<p align="center">
  <img width="793" alt="Remove" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/00071022-a78b-4b36-bd1d-eaf64aad49fc">
</p>

<br>

## Import New package

Importing the new package is the same as importing other normal packages in Unity. 
Select the package of HISPlayer SDK and import it.

**Assets > Import Package > Custom Package > HISPlayerSDK.unitypackage**

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
If you received a license key from HISPlayer, please input the license key in the License Key field.

<p align="center">
<img width=70% alt="image" src="https://github.com/HISPlayer/UnityWebGL-SDK/assets/47497948/50b10c75-c6e0-438d-ba1f-da6e66d51eed">
</p>

If the license key is not valid, the player won’t work and will throw an error message. License key is not required for Unity Editor usage.
