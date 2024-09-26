# Using iOS HLS Downloader

HISPlayer iOS for Unity can download an HLS stream and, once it has been downloaded, play it as [**local content**](./local-files.md).

For this actions iOS device doesn't need to ask for permissions.

# Download the HLS stream.
To download the HLS stream, first call the **DownloadStream** API. The stream will be saved in your [**Persistent Data Path**](./local-files.md#Persistent-Data-Path):

```C#
public class HISPlayeriOSDownloaderSample : HISPlayerManager
{
    protected void DownloadStream()
    {
        DownloadStream("https://MyHLSStreamURL.m3u8", "MyStreamTitle");
    }
}
```
You can track the progress of the HLS download by overriding the function **EventOnDownloadProgress**.

```C#
public class HISPlayeriOSDownloaderSample : HISPlayerManager
{
    protected override void EventOnDownloadCompleted(HISPlayerEventInfo eventInfo)
        {
            // Change Downloading Stream text
            if (eventInfo.stringInfo == "MyStreamTitle")
                Debug.Log("Downloading Stream: " + eventInfo.param1 + "%. Stream Title: " + eventInfo.stringInfo + ".");
        }
}
```

# Play the downloaded video

Override the **EventOnDownloadCompleted**. This overrided function will be called when the stream has finished downloading. You can use it to directly start the video playback or decide to playback the video later at any given time.
To start playing the video, just input the previously settled stream's title, and HISPlayer will automatically find the video in your [**Persistent Data Path**](./local-files.md#Persistent-Data-Path).

Here is an example of how this event could be used to play the stream just after it has finished downloading:

```C#
public class HISPlayeriOSDownloaderSample : HISPlayerManager
{
    protected override void EventOnDownloadProgress(HISPlayerEventInfo eventInfo)
        {
            // 1. Prepare the StreamProperties to be added
            StreamProperties stream = new StreamProperties();
            stream.renderMode = HISPlayerRenderMode.RawImage;
            stream.rawImage = rawImage1;
            stream.autoPlay = true;

            // 2. Add prepared stream
            AddStream(stream);

            // 3. Add the downloaded video content to the stream. eventInfo.stringInfo corresponds to
            // the relative path to the Application.PersistentDataPath. You can save this value to
            // open the content at any point after this event has been triggered
            AddVideoContent(totalScreens, eventInfo.stringInfo);
            totalScreens++;

            base.EventOnDownloadCompleted(eventInfo);
        }
}
```

# Delete downloaded HLS Streams from iOS device

To delete a specific downloaded HLS stream from [**Persistent Data Path**](./local-files.md#Persistent-Data-Path) (application's path), use the **DeleteDownloadedStream** API:

```C#
public class HISPlayeriOSDownloaderSample : HISPlayerManager
{
    protected void DeleteDownloadedStreamFunction(string streamTitle)
    {
        DeleteDownloadedStream(streamTitle);
    }
}
```
To delete all streams from the [**Persistent Data Path**](./local-files.md#Persistent-Data-Path), use the **DeleteAllDownloadedStreams** API: 

```C#
public class HISPlayeriOSDownloaderSample : HISPlayerManager
{
    protected void DeleteAllDownloadedStreamFunction()
    {
        DeleteAllDownloadedStreams();
    }
}
```
