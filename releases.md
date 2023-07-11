# HISPlayer Unity iOS SDK Release Notes
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
