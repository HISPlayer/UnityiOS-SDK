# Import HISPlayer MultiStream Sample

Please, download the sample here -> [**HISPlayer MultiStream Sample**](https://downloads.hisplayer.com/Unity/AllPlatforms/HISPlayer_MultiStream_Sample.unitypackage) 
(no need to download it if you have received it in the email).

Importing the package is the same as importing other normal packages in Unity. Select the downloaded package and import it.

- **Assets > Import Package > Custom Package > HISPlayer_MultiStream_Sample.unitypackage**

<p align="center">
  <img width=50% src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/9cddf00f-9abc-4075-9bc2-ba278b92a7f9">
</p>

- Complete the configuration for iOS ->  [**Configure Unity for iOS**](./setup-guide.md#12-configure-unity-for-ios)

- Open the scene **Assets/HISPlayerMultiStream/Scenes/HISPlayerMultiStream.unity**

<p align="center">
  <img width=60% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/947b66af-5f9f-4277-b9de-831e097c52ef">
</p>

- Import TextMesh Pro Essential

- Input the license key through the Inspector. **HISPlayerMultiStreamController** GameObject -> **HISPlayerMultiStreamController** component -> **License Key**

<p align="center">
  <img width=80% alt="image" src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/af5403d2-1d0c-46c0-b70e-c4217c52d151">
</p>

- Open **File** > **Build Settings** > **Add Open Scenes**

<p align="center">
  <img width=70% alt="ios" src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/4f8f07f3-0d98-4890-b83f-16b6bbdda652">
</p>

- Build and Run

To check how to set up the SDK and API usage, please refer to **Assets/HISPlayerMultiStream/Scripts/HISPlayerMultiStreamController.cs** and **HISPlayerMultiStreamController GameObject** in the Editor.

## MultiStream UI Demo
The UI components in the sample scene are fully modifiable and each stream has its own UI. The sample is intended to show a comprehensive scene using the HISPlayer SDK to help demonstrate features such as play, pause, seek, etc using the multi stream feature. 

<p align="center">
  <img width=55% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/831e1bfa-6b41-4051-83a4-49e5537d9c11">
</p>

<p align="center">
<img width=90% alt="image" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/965817d8-32f8-40f9-9bbc-7471929558ae">
</p>

## Add/Remove Streams and URLs
In order to add/remove streams and URLs, please refer to the component **HISPlayerMultiStreamController** attached to the **HISPlayerMultiStreamController GameObject** in the **Inspector**. 

### Add/Remove Streams

You can add/remove streams by pressing the buttons **+/-** in the **Multi Stream Properties list**. Once a new stream is added, please, select the render mode and the surface where you want to display your videos (Material, Raw Image or RenderTexture). 

<p align="center">
  <img width=70% alt="streams" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/4bae2a6a-16ba-4ba7-ae7a-911a8f0a3185">
</p>

<p align="center">
  <img width=70% alt="render" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/4e93b5bd-c0e8-420b-aa67-fae5c4e59f7c">
</p>

### Change URL
To change the default video URL using your own URL, please replace the element value with your own URL in the **URL list** of the stream you want to modify.

<p align="center">
  <img width=60% alt="image" src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/9f0cd526-bc77-468e-95a3-324def7d4e10">
</p>

### Add/Remove URLs

You can add/remove URLs by selecting one element from the **Multi Stream Properties list** and then pressing the buttons **+/-** in the **Url list**.
For changing the content of the videos, please refer to **[ChangeVideoContent](https://hisplayer.github.io/UnityiOS-SDK/#/hisplayer-api?id=protected-void-changevideocontentint-playerindex-int-urlindex)** API.

<p align="center">
  <img width=70% alt="urls" src="https://github.com/HISPlayer/UnityAndroid-SDK/assets/47497948/bf03d4a3-d1a5-4e4d-b572-10bbe18c1f86">
</p>

