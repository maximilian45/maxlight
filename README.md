# MaxLight
## Alpha 1.0
This is a little tool to get the average screen color of a monitor of choice and send it to an rgb LED strip as fast as possible to tint a whole room in the displayed color. \
It is not another copy of an Ambilight system, but can be used for it if you'd assign Desktop-Areas to different LEDs and update the USB-buffer and Arduino code. \
Instead, it's a room light to destress the eyes and raise the immersive power of entertainment setups, like in this quick/temp. setup:


<p align="center"><img src="https://user-images.githubusercontent.com/29096190/120733553-bbab7e80-c4e7-11eb-9283-43d97362c2dc.gif" width="320" height="160" /></p>



Keeping the CPU usage low was one of the goals, because gaming on my very own setup revealed: \
  my CPU is the performance bottleneck while the GPU stays cool and calm. 

## Using the program: 
```
Set the USB port number yourself. 
Inserting a higher saturation and brightness values in the setup will show you the current color accents of the screen. 
For watching a movie, I'd recommend lower values to get an ambient lighting and smoother transitions. 
Higher saturation values than zero can be used to ignore the 256 shades of grey (from black to white) and 
a higher brighness value ignores dark pixels and raises the overall brightness of the LEDs,
which then adapt only the color of the accents on the display. 
In combination with a low saturation value, a smooth and ambient effect can be created. 
Just play around. 
Btw.: Netflix' desktop app and some other apps and sites with DRM-protection will block the win desktop duplication api from grabbing the frames. 
Workaround: use Firefox or something else... 
```
## Appendix:
The project got compiled by Visual Studios' "Release Mode"  with winSDK and only works on Windows 8.1 and higher and x64. \
More features will come soon. \
'lumos_maxima.cpp' is the Arduino code. 


Known bugs: \
Switching from or to a fullscreen mode programm causes an access loss of the variables or stucks in an api-function. Restart the Program and switch/'Alt+Tab' back to the game within 5 seconds. This accounts to every display mode switch (change of resolution, lockscreen, changing games from window mode to fullscreen, ...).


Porting it to Linux would require a replacement of the AcquireNextFrame() function of the windows desktop duplication api and some other adjustments. \
I'd suggest to grab the backbuffer of the GPU and load it in a \<D3D11Texture2D\>.
