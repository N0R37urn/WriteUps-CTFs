# I_wanna_be_a_streamer
### 169pt Easy

Sorry Mom, I'll work as a streamer.
Watch my stream once in a while.
(H.264 is used for video encoding.)

[Link](../files/for-I-wanna-be-a-streamer.zip)

# Solution

1. Upon visualizing the PCAP file with Wireshark, the RTP protocol was identified, containing an audio track that likely was part of a video stream.

<p align="center">
  <img src="../../Imagenes/LMl3NHKKct.png" width="500" alt="Signal">
</p>

2. It was identified that this is encoded in something called `video H.264`.

3. After conducting an Osint search, I managed to find a GitHub repository [h264extractor](https://github.com/volvet/h264extractor), which contained a plugin to be used in Wireshark to extract these H.264 packets to form a complete video streaming file.

   After struggling for a while with the installation, I managed to install and use it...

<p align="center">
  <img src="../../Imagenes/DlAu9Nk27G.png" width="600" alt="Extraction">
</p>

4. After extracting the video with the .264 extension, I used the command `ffmpeg -probesize 32M -analyzeduration 32M -f h264 -i video_20240623-102629.264 -c copy flag.mp4` to encapsulate the H.264 video stream into an MP4 container without altering the original encoding.

<p align="center">
  <img src="../../Imagenes/rt4hyC1n7M.png" width="600" alt="FFMPEG">
</p>

5. The video was obtained in `MP4` format and thus the flag was secured.

<p align="center">
  <img src="../../Imagenes/Y0nYFsjnTM.png" width="400" alt="FLAG">
</p>

### FLAG{Th4nk_y0u_f0r_W4cthing}


