# Video Streaming

IP Cameras —> Network Switches —> OBS —> Network Switches —> HDMI over IP —> Monitors


## AVer PTZ Camera Streaming

The AVer IP cameras are Pan-Tilt-Zoom (PTZ) models which can stream using either USB, RTSP, or NDI (NDI-HX). Only the AVer PTZ330N devices support native NDI output while the AVer PTZ310 can only stream using RTSP. The benefits of using NDI is a near-native, latency-free stream which can be accessed by any NDI-capable software. This avoids the need to decode the stream 

### Streaming Constraints

- These are mutually-exclusive options
    - RTSP is available when Video Mode is “Streaming”
    - NDI is only available when Video Mode is “NDI”
- Latency is much lower with NDI but increases bandwidth
    - 4Mbps = 580KB/sec.
    - 8Mbps = ~1.8MB/sec.
    - 16Mbps = ~2.9MB/sec.
    - 32Mbps = ~3.8MB/sec.

For purposes of non-broadcast, close-range distribution using 8Mbps is sufficient and has been configured on a per-camera basis already.

## HDMI Streaming/Distribution

[Monoprice Blackbird H.265 Video Extender/Splitter over IP with HDMI](https://www.monoprice.com/product?p_id=43624)

Using the VLC program open a Network stream to one of the following paths:

* rtsp://192.168.10.10/live/main/av_stream
* rtsp://192.168.10.10/live/sub/av_stream

Receiver units will automatically assign themselves an IP address, typically starting at 192.168.10.11 and increments by 1 for each additional device.


## Streaming with OBS

Open Broadcast Studio is a powerful and FREE application used by many vloggers streamers across the internet. The interface is powerful though it takes some use to get familiar with the capabilities. Thankfully, given it's ubiquitious nature online there is no shortage of videos on both basics and advanced topics.

**Software Requirements**

- Open Broadcast Studio (OBS): [https://obsproject.com/download](https://obsproject.com/download) (v32+)
- NDI Tools: [https://ndi.video/tools/](https://ndi.video/tools/) (macOS Ventura or later)
    - Use the NDI Video Monitor from the NDI Tools to select and view the stream to test access.
- OBS NDI Library/Runtime: [https://github.com/DistroAV/DistroAV/releases](https://github.com/DistroAV/DistroAV/releases)
    - [https://github.com/DistroAV/DistroAV/wiki/1.-Installation#required---ndi-runtime](https://github.com/DistroAV/DistroAV/wiki/1.-Installation#required---ndi-runtime) 
- Homebrew can install both "distroav" and "libndi" (NDI runtime), see below.


### Install Homebrew and Plugins for OBS

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

brew install ffmpeg distroav
brew install —-cask ndi-tools
```

### Video Compositing

- Open OBS (after installing all libraries and runtime packages)
- OBS main window -> Settings (lower right)
    - Video
        - Base (Canvas) Resolution: 1920x1080
        - Output (Scaled) Resolution: 1920x1080
        - Common FPS Values: 30
    - Advanced
        - Color Format: NV12
        - Color Space: Rec. 709
        - Color Range: Limited (or Partial)
    - Output [Advanced] -> Streaming
    - Save (OBS may need to restart)
- For NDI Sources: OBS main window -> Sources (lower mid-left)
    - Add Source [+]
    - Look for "NDI Source" in the list of sources
    - For “Source name” select the camera stream
    - Use the highest quality/bandwidth
    - Do not enable hardware acceleration
    - Use the Low latency option
    - Use limited YUV color space
- For USB Sources: OBS main window -> Sources (lower mid-left)
    - Add Source [+]
    - Look for "Media Source" in the list of sources
    - Uncheck "Local File" and use the device IP
    - eg. `rtsp://<camera_ip>/live_st1`
    - Use the highest quality/bandwidth
    - Do not enable hardware acceleration
    - Use the Low latency option
    - Use limited YUV color space
- OBS Scenes
    - Create a scene for each camera, with necessary settings for bandwidth, frame rate, etc.
    - Add labels or other items to each camera scene as desired.
    - Create new scenes which then use the camera scenes directly, eg. "2x2 Grid":
        - Add each camera scene to the new scene (essentially "nested scenes").
        - Right-click —> Transform —> Edit Transform (resolution: 960x540)
        - Arrange as desired (dragging or using offset parameters via Transform)


### HDMI Video Output

In order to get a video feed from OBS you must use a Mini-DisplayPort to HDMI adapter with the iMac, and select Full Screen Projector from the OBS menu (right-click in the preview screen for options). This will treat the HDMI output as a second monitor with a full-screen preview of the live feed shown in the OBS interface.

**Note:** HDMI output from the iMac typically adds HDCP (HD Copy Protection) to the signal which CANNOT be propagated through the Blackbird devices. In order to bypass this a special HDMI splitter is used to help "strip" the HDCP from the HDMI signal. This works by leveraging a known issue with some cheap splitters which improperly implement HDCP and therefore acts as a "HDCP Bypass" and allows the transcoding device to get a clean signal that it can propagate.


### NDI Streaming Output

If needed, the DistroAV plugin for OBS allows you to enable NDI output directly, without need for a separate streaming configuration. Once enabled, NDI output begins immediately.

- OBS main menu -> Tools -> DistroAV NDI Settings
    - [X] Main Output
    - Main output name: obs
    - OK to save


### OBS Clean Slate

Should things go completely wrong with OBS use the following to uninstall and remove the program and any plugins installed.

```
# remove the obs application
rm -rf /Applications/OBS.app

# remove all obs user data
rm -rf ~/Library/Application\ Support/obs-studio
rm -rf ~/Library/Preferences/com.obsproject.obs-studio.plist
rm -rf ~/Library/Caches/com.obsproject.obs-studio
rm -rf ~/Library/Logs/obs-studio

# remove any lingering plugins
rm -rf ~/Library/Application\ Support/obs-studio/plugins
rm -rf ~/Library/Application\ Support/obs-studio/obs-plugins

# find packages
pkgutil --pkgs | grep -i ndi

# forget pkg receipts
sudo pkgutil --forget com.newtek.ndi.runtime
sudo pkgutil --forget com.obsproject.obs-ndi

# remove files
sudo rm -rf /Library/NDI /Library/Frameworks/*NDI*
rm -rf ~/Library/Application\ Support/obs-studio/*ndi*

# remove lingering user data
sudo rm -rf /Library/NDI
sudo rm -rf /Library/Frameworks/NDI.framework
sudo rm -rf /Library/Frameworks/Processing.NDI.Lib.framework

# reboot
reboot now

# then
brew install distroav
```