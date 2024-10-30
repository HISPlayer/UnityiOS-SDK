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

# Related API

### Event and Virtual Options
* **public enum HISPlayerEvent**: The list of events provided by HISPlayer SDK for using HLS Downloader functionalities. The events can be used with the virtual functions in the next section:
    * **HISPLAYER_EVENT_DOWNLOAD_COMPLETED**
    * **HISPLAYER_EVENT_DOWNLOAD_PROGRESS**


#### protected virtual void EventOnDownloadCompleted(HISPlayerEventInfo eventInfo)
Override this method to add custom logic when **HISPlayerEvent.HISPLAYER_EVENT_DOWNLOAD_COMPLETED** is triggered.
This event occurs whenever a stream that was being downloaded has ended the download process, and it's ready to be played.

<table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>stringInfo</td>
    <td>Relative path where the stream has been stored. This will equal to the title settled to the video. The path is relative to the Application.persistentDataPath,which in iOS corresponds to    /var/mobile/Containers/Data/Application/<guid>/Documents. Save it for later plaback of such stream.</td>
  </tr>
</table>

#### protected virtual void EventOnDownloadProgress(HISPlayerEventInfo eventInfo)
Override this method to add custom logic when **HISPlayerEvent.HISPLAYER_EVENT_DOWNLOAD_PROGRESS** is triggered.
This event occurs whenever a HLS stream is being downloaded, to retrieve the progress of such download.

<table>
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>param1</td>
    <td>The percentage of the download progress of a certain stream.</td>
  </tr>
   <tr>
    <td>stringInfo</td>
    <td>Title of the stream that is being downloaded. This title is settled by the user when calling the DownloadStream API.</td>
  </tr>
</table>

### Non-virtual Functions

#### public void DownloadStream(string url, string videoTitle)
Download an HLS Stream. Stream will be automatically saved on the Application.PersisentDataPath (/var/mobile/Containers/Data/Appligation/<guid>/Documents). If 2 downloaded contents have the same video title, the last one will overrite the first one. Avoid using non english characters, dots, slashes and any other kind of special character. The **url** refers to the URL to the HLS stream. **videoTitle** is the name of the saved stream and will allow to reproduce it once it has been downloaded.

#### public void DeleteDownloadStream(string videoTitle)
Delete a specific downloaded HLS Stream. **videoTitle** is the name  of the stream that will be deleted from the device.

#### public void DeleteAllDownloadedStreams()
Delete all downloaded streams that have been stored in the Application.PersistentDataPath.
