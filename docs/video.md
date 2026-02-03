# Video Streaming

IP Cameras —> Network Switches —> OBS —> Network Switches —> HDMI over IP —> Monitors


## AVer PTZ Camera Streaming

AVer PTZ330N Streaming

N = NDI - Network Device Interface

AVer PTZ Manager (Windows-only)
Requires Login: admin/admin

For NDI streaming MDNS discovery will show cameras under the "_ndi._tcp." group:

- AVER (PTZ330N)
- AVer.local.
- `<ip_address>:<port>` (eg. 10.1.0.188:5961)
- groups=public
- discovery=5960

After locating the camera works, you can’t add it without an account and password.

* Default: admin/admin
* Current: wildcat/theatre

For the AVer PTZ310, select a Media Source in OBS, uncheck “Local File” and use the device IP:
`rtsp://<camera_ip>/live_st1`

### Streaming Constraints

- These are mutually-exclusive options
    - RTSP is available when Video Mode is “Streaming”
    - NDI is only available when Video Mode is “NDI”
- Latency is much lower with NDI but increases bandwidth
    - 4Mbps = 580KB/sec.
    - 8Mbps = ~1.8MB/sec.
    - 16Mbps = ~2.9MB/sec.
    - 32Mbps = ~3.8MB/sec.


## Blackbird Streaming

Using the VLC program open a Network stream to one of the following paths:

* rtsp://192.168.10.10/live/main/av_stream
* rtsp://192.168.10.10/live/sub/av_stream


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

## Video Compositing

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
- OBS main window -> Sources (lower mid-left)
    - Add Source [+]
    - Look for "NDI Source" in the list of sources
    - For “Source name” select the camera stream
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


## Streaming Configuration (Advanced)

Enabling NDI Output

- OBS main menu -> Tools -> DistroAV NDI Settings
    - [X] Main Output
    - Main output name: obs
    - OK to save (NDI output begins immediately)


## OBS Clean Slate

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