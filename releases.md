# HISPlayer Unity iOS SDK Release Notes

### Version 4.14.2
##### December 30, 2025
- [**Added**] EventNetworkConnected, ErrorNetworkFailed and auto network reconnection during video playback.

### Version 4.14.1
##### December 23, 2025
- [**Improvement**] Updated eventType of EventPlaybackSeekEnd to output HISPLAYER_EVENT_PLAYBACK_SEEK_END.

### Version 4.14.0
##### December 18, 2025
- [**Improvement**] Improved compatibility with App Store submission related to symbol name collisions with Apple system libraries.
- [**Improvement**] Improved volume change event handling to ensure HISPLAYER_EVENT_VOLUME_CHANGE is triggered consistently across all platforms.
- [**Improvement**] Updated GetProgramDateTimeEpoch to return the exact Epoch time of the current frame.
- [**Improvement**] Improved seek event handling to ensure HISPLAYER_EVENT_PLAYBACK_SEEK_END is consistently triggered across all platforms.

### Version 4.13.0
##### November 28, 2025
- [**Added**] New playback seek events: HISPLAYER_EVENT_PLAYBACK_SEEK_BEGIN and HISPLAYER_EVENT_PLAYBACK_SEEK_END with their respective overridable functions. HISPLAYER_EVENT_PLAYBACK_SEEK and the overridable function are deprecated.
- [**Added**] Customizable logging system allowing configuration of logLevel, showPlatform, showColorized, and showTimestamp.
- [**Added**] GetProgramDateTimeEpoch and GetProgramDateTimeString APIs to obtain the EXT-X-PROGRAM-DATE-TIME information from HLS streams.

### Version 4.12.0
##### October 29, 2025
- [**Improvement**] Optimized SetPlaybackSpeed behavior to follow the video playback state.
- [**Improvement**] Improved the UI appearance of HISPlayerManager in the inspector.
- [**Improvement**] Improved log.

### Version 4.10.0
##### September 11, 2025
- [**Improvement**] Optimized RemoveStream after Stop.
- [**Improvement**] Editor no longer clears console logs after stopping Play mode.
- [**Improvement**] Improved log when releasing player.
- [**Improvement**] Improved package architecture for multiple packages combination.

### Version 4.8.0
##### July 7, 2025
- [**Improvement**] Enhancement to InspectorGUI to dynamically show/hide certain options.

### Version 4.4.0
##### September 10, 2024
- [**Added**] Release API is called automatically when stopping the Editor, changing scenes or closing the app
- [**Added**] EventVideoSizeChange - eventInfo.param3 is catching the internal rotation value of the original video
- [**Improvement**] Optimized error log messages

### Version 4.3.0
##### August 8, 2024
- [**Added**] **HISPLAYER_EVENT_VIDEO_SIZE_CHANGE** and **EventVideoSizeChange**.
    - This event occurs whenever the internal video size of the current track changes
- [**Added**] New HISPlayer Video Uploader feature. Turn local videos into streaming videos such as HLS or DASH. This videos are going to be stored in our server for you. Please, on the Editor refer to:
    - [HISPlayer Video Upload documentation](https://hisplayer.github.io/UnityVideoUpload/#/)
- [**Added**] Custom resources to play 180/360 videos
    - Packages > HISPlayer SDK > HISPlayer > Resources > Materials > **HISPlayer360Material.mat**
    - Packages > HISPlayer SDK > HISPlayer > Resources > Materials > **HISPlayer180Material.mat**
    - Packages > HISPlayer SDK > HISPlayer > Scripts > Shaders > **HISPlayer360Shader.shader**
    - Packages > HISPlayer SDK > HISPlayer > Scripts > RenderTextures > **HISPlayer360RenderTexture.rendertexture**
- [**Improvement**] Optimized HISPlayer Settings log messages
- [**Improvement**] Optimized Event and Error listeners
- [**Improvement**] Optimized license checking
- [**Improvement**] Optimized HISPlayer API function commentaries to be more clear
- [**Improvement**] Optimized runtime log messages

### Version 3.4.1
##### April 23, 2024
- [**Improvement**] Improvement of software robustness

### Version 3.4.0
##### April 10, 2024
- [**Added**] Multi stream support on Windows Editor
- [**Added**] HISPLAYER_ERROR_PLATFORM_NOT_REGISTERED error event
- [**Added**] URL_EXTENSION, HLS and DASH MIME Types support. Please, refer to HISPlayerMimeTypes on [HISPlayer API](https://hisplayer.github.io/UnityiOS-SDK/#/hisplayer-api)
    -  URL_EXTENSION (Default)
    -  HLS
    -  DASH
- [**Improvement**] Optimized HISPlayer Settings
    - A warning message will be displayed in case a field required by HISPlayer SDK is missing

### Version 3.3.0
##### January 25, 2024
- [**Added**] New API to change video content using the URL string as a parameter:
    - **ChangeVideoContent(int playerIndex, string url)**
    - **ChangeVideoContent(int playerIndex, string url, string keyServerURI, string tokenKey = "", string tokenValue = "")**
- [**Improvement**] Optimized error logs
- [**Improvement**] Optimized ChangeVideoContent API with DRM for iOS

### Version 3.2.0
##### December 7, 2023
- [**Added**] AutoTransition and LoopPlayback APIs to multiplatform SDK
- [**Added**] Local content support (Unity StreamingAssets) to multiplatform SDK
- [**Added**] Unity 2023 support to multiplatform SDK
- [**Improvement**] Remove http setting from HISPlayer Settings window

### Version 3.1.1
##### November 23, 2023
- [**Improvement**] Improvement of software robustness

### Version 3.1.0
##### October 11, 2023
- [**Improvement**] Improvement of software robustness

### Version 3.0.0 (Multiplatform SDK)
##### September 5, 2023
The iOS SDK is moved to multiplatform HISPlayerSDK (Android, iOS, macOS, WebGL, Windows)

Starting from version 3.0.0, the iOS SDK is part of multiplatform SDK

### Version 2.13.0
##### December 5, 2023
- [**Added**] Local documentation
- [**Update**] HISPlayer Settings is now visible under 'Tools' Unity window
    - Refer to [Configure Unity for iOS](https://hisplayer.github.io/UnityiOS-SDK/#/setup-guide?id=_12-configure-unity-for-ios) 
- [**Improvement**] Improvement of software robustness.

### Version 2.12.0
##### October 24, 2023
- [**Added**] Unity 2023 support

### Version 2.11.0
##### October 18, 2023
- [**Added**] LoopPlayback API to loop the current playback. This will trigger HISPlayerEvent.HISPLAYER_EVENT_END_OF_CONTENT
    - Refer to [Stream Properties - LoopPlayback](https://hisplayer.github.io/UnityiOS-SDK/#/hisplayer-api)
- [**Added**] AutoTransition API to change the playback to the next video in the playlist. This will trigger the HISPlayerEvent.HISPLAYER_EVENT_AUTO_TRANSITION
    - Refer to [Stream Properties - AutoTransition](https://hisplayer.github.io/UnityiOS-SDK/#/hisplayer-api) 

### Version 2.10.0
##### September 21, 2023
- [**Added**] [Custom Shaders for Linear Color Space](/shaders.md)
- [**Added**] Network lost event
- [**Added**] Local playback support from StreamingAssets and PersistentDataPath

### Version 2.9.0
##### September 7, 2023
- [**Added**] MultiStream with more than one DRM contents
- [**Added**] HISPlayer Settings 
- [**Improvement**] Optimized loading the video contents
- [**Improvement**] Optimized Release API for DRM content
- [**Improvement**] Optimized EndOfContent event
- [**Improvement**] Optimized DRM HLS stream playback

### Version 2.8.0
##### August 7, 2023
- [**Added**] Playback Speed Controller. Values must be greater than 0 and less than or equal to 8.
    - void SetPlaybackSpeedRate(int playerIndex, float speed)
    - float GetPlaybackSpeedRate(int playerIndex)

### Version 2.7.0
##### July 28, 2023
- [**Added**] Multistream support
    - [**Improvement**] AddStream and RemoveStream functions can handle more than one stream
- [**Added**] Audio-Track-Selection support
    - HISPlayerAudioTrack[] GetAudioTrackList(int playerIndex)
    - int GetAudioCount(int playerIndex)
    - string GetAudioID(int playerIndex, int audioTrackIndex)
    - string GetAudioLanguage(int playerIndex, int audioTrackIndex)
    - void SelectAudioTrack(int playerIndex, int audioTrackIndex)
- [**Added**] Video-Track-Selection support
    - HISPlayerTrack[] GetTracks(int playerIndex)
    - int GetTrackBitrate(int playerIndex, int trackIndex)
    - int GetTrackWidth(int playerIndex, int trackIndex)
    - int GetTrackHeight(int playerIndex, int trackIndex)
    - int GetTrackID(int playerIndex, int trackIndex)
    - int GetTrackCount(int playerIndex)
    - void SelectTrack(int playerIndex, int bitrate)
- [**Added**] ChangeVideoContent at runtime support
    - void ChangeVideoContent(int playerIndex, int urlIndex)
- [**Improvement**] Optmized AddVideoContent function
- [**Improvement**] Optimized Release function for MacOS Editor and iOS

### Version 2.6.0
##### July 11, 2023
- [**Added**] Audio-Track-Selection support for MacOS Editor
    - HISPlayerAudioTrack[] GetAudioTrackList(int playerIndex)
    - int GetAudioCount(int playerIndex)
    - string GetAudioID(int playerIndex, int audioTrackIndex)
    - string GetAudioLanguage(int playerIndex, int audioTrackIndex)
    - void SelectAudioTrack(int playerIndex, int audioTrackIndex)

### Version 2.5.0
##### July 4, 2023
- [**Added**] Subtitles support for MacOS Editor and iOS
    - HISPlayerCaptionTrack[] GetCaptionTrackList(int playerIndex)
    - int GetCaptionsCount(int playerIndex)
    - void EnableCaptions(int playerIndex, bool enabled)
    - string GetCaptionID(int playerIndex, int ccTrackIndex)
    - string GetCaptionLanguage(int playerIndex, int ccTrackIndex)
    - void SelectCaptionTrack(int playerIndex, int ccTrackIndex)
- [**Improvement**] Optimized AddNewStream API on Windows Editor and iOS
- [**Improvement**] Optimized Release API on Windows Editor
- [**Improvement**] Optimized SetupPlayer API during runtime for Windows Editor

### Version 2.4.0
##### June 15, 2023
- [**Improvement**] Optimized loading Inka DRM contents when internet connection is off.

### Version 2.3.0
##### May 31, 2023
- [**Added**] Added Inka DRM support.
- [**Improvement**] Optimized GetVideoDuration() API.

### Version 2.2.0
##### May 25, 2023
- [**Added**] MacOS Editor support.

### Version 2.1.0
##### April 28, 2023
- [**Improvement**] The iOS package is combined with Android package.

### Version 1.1.0
##### April 20, 2023
- [**Added**] HISPlayer iOS SDK is now compatible with other platform SDKs in the same project.
- [**Added**] HISPlayerAPI namespace has been modified to HISPlayeriOSAPI.

### Version 1.0.0
##### April 14, 2023
- [**Added**] Initial release of HISPlayer iOS SDK for Unity.
