# Overview
Youtube-dl or YTDL is a command-line program which downloads YouTube videos into a local file. The file can be downloaded as a video or audio file with a variety of formats.
Download YTDL from the [GitHub repository](https://github.com/ytdl-org/youtube-dl). A video must be public or unlisted to be downloaded.

This is a simple guide for downloading full or partial videos and playlists on Windows. For a complete guide to YTDL and its features, refer to the [YTDL README](https://github.com/ytdl-org/youtube-dl#readme)

It's recommended that you download the FFmpeg command-line program to access a wider variety of file extension formats. 
Download [here](https://www.ffmpeg.org/).

# Getting Started
**NOTE:** If a string in the following descriptions contains parentheses ( ), do not include the parentheses in Command Prompt.
After downloading the YTDL program, move the file to your desired drive.

1. Open Command Prompt.
2. Type `(Drive Letter):` where YTDL is located and hit Enter
   
     <sub>Ex. YTDL is located on the C drive. Type `C:`</sub>
   
3. If you placed YTDL in a folder on the drive, type `cd (Folder Name)` and hit Enter

    <sub>Ex.  YTDL is located in a folder called YTDL which is in the C drive. Type `cd YTDL`</sub>


## Downloading Videos
YTDL will automatically attempt to download the best quality video available if no file extension strings are specified.
You can choose the format of the video file with the string `-f bestvideo[ext=(Video File Extension)]`.
Available video file extensions include `3gp, flv, mp4, webm`. FFmpeg allows for additional file extensions.

### Single Video
To download a single video, use the following strings in Command Prompt after following the [Getting Started](https://github.com/MyOwnSpace99/Youtube-dl-command-lines/edit/main/README.md#getting-started) step.
| String | Function |
|--------|----------|
|`youtube-dl.exe`| Enables Youtube-dl.|
|`-f`| Allows file format strings to alter the video file.|
|`"bestvideo[ext=(Video File Extension)]"`| Allows you to specify the video file extension.|
|`(YouTube Video URL)`| The link to the YouTube video.|


*Example template:*


4. Type `youtube-dl.exe -f bestvideo[ext=(Video File Extension)] (YouTube Video URL)` and hit Enter.


### Partial Download
**NOTE**: Partially downloading a YouTube video or audio requires YT-DLP, a Youtube-dl fork which adds additional functions. Download [here](https://github.com/yt-dlp/yt-dlp). It also requires [FFmpeg](https://github.com/MyOwnSpace99/Youtube-dl-command-lines/edit/main/README.md#overview).

You can download a specific portion of a video with additional file format strings.
| String | Function |
|--------|----------|
|`yt-dlp`| Enables YT-DLP.|
|`-f`| Allows file format strings to alter the video file.|
|`"bestvideo[ext=(Video File Extension)]"`| Allows you to specify the video file extension.|
|`--external-downloader ffmpeg`| Enables FFmpeg.|
|`--external-downloader-args`| Enables following argument strings to the external downloader.|
|`"ffmpeg_i:-ss 00:00:00.00 -to 00:00:00.00"`| Specifies the portion of the video to be downloaded where `-ss 00:00:00.00` is the time to start the download and `-to 00:00:00.00` is the time to end the download.|
|`"ffmpeg_i:-ss 00:00:00.00 -t (Time in Seconds)"`| Specifies the portion of the video to be downloaded where `-ss 00:00:00.00` is the time to start the download and`-t (Time in Seconds)` is the duration of the download in seconds.|
|`(YouTube Video URL)`| The link to the YouTube video.|


*Example template:*


4. Type `yt-dlp -f "bestvideo[ext=(Video File Extension)]" --external-downloader ffmpeg --external-downloader-args "ffmpeg_i:-ss 00:00:00.00 -to 00:00:00.00" "(YouTube URL)"` and hit Enter.


### Playlist
You can download a YouTube playlist with additional file format strings.
| String | Function |
|--------|----------|
|`youtube-dl.exe`| Enables Youtube-dl.|
|`"bestvideo[ext=(Video File Extension)]"`| Allows you to specify the video file extension.|
|`--playlist`| Specifies that a playlist is to be downloaded.|
|`-start (Video's Number in Playlist)`| Specifies at which video to start downloading the playlist where `(Video's Number in Playlist)` is the video's position in the playlist. *Ex. Second video is 2, third video is 3, etc.*|
|`(YouTube Playlist URL)`| The link to the YouTube playlist.|


*Example template:*


4. Type `youtube-dl.exe -f bestvideo[ext=(Video File Extension)] --playlist-start (Video's Number in Playlist) (YouTube Playlist URL)` and hit Enter.


## Downloading Audio
YTDL will automatically attempt to download the best quality audio available if no file extension strings are specified.
You can choose the format of the audio file with the string `-f bestaudio[ext=(Audio File Extension)]`.
Available audio file extensions include ` aac, flv, m4a, mp3, ogg, wav`. FFmpeg allows for additional file extensions.

### Single Audio
To download a single audio, use the following strings in Command Prompt after following the [Getting Started](https://github.com/MyOwnSpace99/Youtube-dl-command-lines/edit/main/README.md#getting-started) step.
| String | Function |
|--------|----------|
|`youtube-dl.exe`| Enables Youtube-dl.|
|`-f`| Allows file format strings to alter the video file.|
|`"bestaudio[ext=(Audio File Extension)]"`| Allows you to specify the video file extension.|
|`(YouTube Video URL)`| The link to the YouTube video.|

*Example template:*


4. Type `youtube-dl.exe -f bestaudio[ext=(Audio File Extension)] (YouTube Video URL)` and hit Enter.


### Partial Audio
**NOTE**: Partially downloading a YouTube video or audio requires YT-DLP, a Youtube-dl fork which adds additional functions. Download [here](https://github.com/yt-dlp/yt-dlp). It also requires [FFmpeg](https://github.com/MyOwnSpace99/Youtube-dl-command-lines/edit/main/README.md#overview).

You can download a specific portion of an audio with additional file format strings.
| String | Function |
|--------|----------|
|`yt-dlp`| Enables YT-DLP.|
|`-f`| Allows file format strings to alter the audio file.|
|`"bestaudio[ext=(Audio File Extension)]"`| Allows you to specify the audio file extension.|
|`--external-downloader ffmpeg`| Enables FFmpeg.|
|`--external-downloader-args`| Enables following argument strings to the external downloader.|
|`"ffmpeg_i:-ss 00:00:00.00 -to 00:00:00.00"`| Specifies the portion of the audio to be downloaded where `-ss 00:00:00.00` is the time to start the download and `-to 00:00:00.00` is the time to end the download.|
|`"ffmpeg_i:-ss 00:00:00.00 -t (Time in Seconds)"`| Specifies the portion of the audio to be downloaded where `-ss 00:00:00.00` is the time to start the download and`-t (Time in Seconds)` is the duration of the download in seconds.|
|`(YouTube Video URL)`| The link to the YouTube video.|


*Example template:*


4. Type `yt-dlp -f "bestaudio[ext=(Audio File Extension)]" --external-downloader ffmpeg --external-downloader-args "ffmpeg_i:-ss 00:00:00.00 -to 00:00:00.00" "(YouTube URL)"` and hit Enter.


### Playlist
You can download a YouTube playlist with additional file format strings.
| String | Function |
|--------|----------|
|`youtube-dl.exe`| Enables Youtube-dl.|
|`"bestaudio[ext=(Audio File Extension)]"`| Allows you to specify the audio file extension.|
|`--playlist`| Specifies that a playlist is to be downloaded.|
|`-start (Video's Number in Playlist)`| Specifies at which video to start downloading the playlist where `(Video's Number in Playlist)` is the video's position in the playlist. *Ex. Second video is 2, third video is 3, etc.*|
|`(YouTube Playlist URL)`| The link to the YouTube playlist.|


*Example template:*


4. Type `youtube-dl.exe -f bestaudio[ext=(Audio File Extension)] --playlist-start (Video's Number in Playlist) (YouTube Playlist URL)` and hit Enter.

