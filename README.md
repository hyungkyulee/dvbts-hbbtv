# dvbts-hbbtv
dvb stream generation with hbbtv AIT singnaling

Licence is under EBU, ffmpeg, and opencaster(avalpa)

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

### build
Edit the python file 'create-metadata-ts.py' with the hbbtv app url at the variable of 'appli_root' and 'appli_path'
``` python
# parameters reported into the AIT to signalize a broadband application.
appli_name = ["EBU-CPA1", "EBU-CPA2"] #application name
appli_root = ["https://devhbb.tvp.pl/hbbtv-35/apps/weather/", "http://itv.mit-xperts.com/hbbtvtest/"] #URL base of transport_protocol_descriptor
appli_path = ["index.php", "index.php"]  #initial_path_bytes of simple application descriptor. So the application path will be "http://my_application_root_path/myHbbTV-app/index.html"
organisationId = [10, 10]  	 # this is a demo value, dvb.org should assign an unique value
applicationId = [1001, 1002] # this is a demo value. This number corresponds to a trusted application. 
```

run the shell script
```
make-stream.sh
```

### Inject .ts stream
Find .ts stream at '/output' folder
inject the .ts stream via Dectek modulator

