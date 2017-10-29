# SFS-Mobile-TV

Portable TV

hardware
-----
7 inch screen in landscape mode  
pi 2  
micro analog amplifier  
micro power supply  
hauppauge WinTV-HVR-950Q  
usb twist extension for tv device  
room for lithium polymer or convention lithium ion batteries

software
-----
xfce  
easystroke  
omxplayer

gestures
-----
pause - square shape  
skip - counterclockwise and clockwise  
channel change - swipe left and right  
volume change - swipe up and down  
quit - X shape  

notes on early 7" Waveshare screen
-----
touch requires special python driver  
touch does not work properly with any orientation than standard landscape  
touch does not work properly with different framebuffer resolution  
screen is capacitive and does not require calibration but is single touch

Pi and HDTV explained
-----
Over the air TV in USA is called ATSC.  ATSC transmits an MPEG2 transport stream.  Open source decoders such as those used by Mplayer or VLC can be used but they use the CPU only on the Pi.  Larger computers have more open standards so these same programs can sometimes use additional hardware for decoding on those devices.  If you want to decode MPEG2 in hardware on the Pi you will need to buy the MPEG2 license.  If you do not want to use the license for any number of reasons then VLC can play back the stream reasonably well on the Pi 2 with some modifications.  First of all the framebuffer resolution must be set to 1280x768 which works well to scale up 800x480 or any other resolution 1280x720 or above.  This is because scaling in any other way is too "expensive" to do on the CPU.  This also means 1080i content will be too large and off screen and 480p content will be in a window.  Also the ffmpeg settings will need to be configured in VLC particularly setting "Skip Frame" to setting "2".  This allows for decent but not perfect playback of 720p video.  Playback is entirely perfect with omxplayer and the MPEG2 license.

