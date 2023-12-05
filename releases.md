# HISPlayer Unity iOS SDK Release Notes

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
