# dvbts-hbbtv
dvb stream generation with hbbtv AIT singnaling

Licence is under EBU, ffmpeg, 

## Developmene environment

### ffmpeg installation 
source git : git clone https://git.ffmpeg.org/ffmpeg.git ffmpeg

on Mac (by Homebrew)
```
brew install ffmpeg
```
 * on Windows, please download zip file and install it and add the environment path

### opencaster installation 
download opencaster source, and copy it to project root
build opencaster
```
make install
```
sudo rm -rf /Library/Developer/CommandLineTools
xcode-select --install
cd /Library/Developer/CommandLineTools/Packages/
open macOS_SDK_headers_for_macOS_10.14.pkg


### change permission 
```
chmod 755 ./*
```
