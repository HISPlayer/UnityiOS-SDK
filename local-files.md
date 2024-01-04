# Playing Local Files

HISPlayer iOS for Unity can play local content from both [**Unity Streaming Assets**](./local-files.md#Unity-Streaming-Assets) and
the [**Persistent Data Path**](./local-files.md#Persistent-Data-Path) (application's path). 

Keep in mind the SDK will look for the local video first on the **Unity Streaming Assets** so a file with the same name on the 
**Persistent Data Path** won't be played.

<br>

For this actions iOS device doesn't need to ask for permissions.

## Unity Streaming Assets
To use this format, it’s necessary to create a new folder into the **Assets** folder of Unity named **StreamingAssets**.

<p align="center">
<img width="350" alt="image" src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/cc52faf6-b7cb-4121-8e75-a548c0e95280">
</p>

The next step is to add a video content inside the folder and pass the name (**with the extension**) to the **Multi Stream Properties**.
&nbsp;

<p align="center">
<img src="https://github.com/HISPlayer/UnityiOS-SDK/assets/47497948/89411ca9-952e-494b-9bfc-14a6e14b70a1">
</p>

In case that subfolders are created inside StreamingAssets, the path of the file **must include the subfolder’s name** inside the field
of Multi Stream Properties, e.g, with a subfolder named **“MyVideos”** the following path must be used: 

**MyVideos/localPlayback.mp4** 
&nbsp;

## Persistent Data Path
The [Persistent Data Path](https://docs.unity3d.com/ScriptReference/Application-persistentDataPath.html) is the internal path of the application.
Unity allows you to access that folder from the C-sharp code with **Application.persistentDataPath**.

The returned path on iOS will be: **/var/mobile/Containers/Data/Application/\<guid>/Documents**.

The HISPlayer SDK will take this path as the entry point to begin to search the desired local content.

In case that subfolders are created inside *Application.persistentDataPath* , the path of the file **must include the subfolder’s name** inside the field
of Multi Stream Properties, e.g, with a subfolder named **“MyVideos”** the following path must be used: 

**MyVideos/localPlayback.mp4** 
&nbsp;
