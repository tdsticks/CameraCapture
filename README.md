CameraCapture
=============

Lightweight python camera motion detection script, by brainflakes


http://www.raspberrypi.org/phpBB3/viewtopic.php?f=43&amp;t=45235

by brainflakes » Mon May 27, 2013 9:22 pm
Hi guys, as a first camera board project I've created a simple and efficient motion detection script in Python using PIL.

While watching for motion it pipes a thumbnail image from raspistill at around 1fps to analyse (it keeps everything in memory to avoid wearing out the SD card). Once motion is detected it calls raspistill again to write a high-res jpeg to disk.

It also checks free disk space and if under a set limit it starts to delete the oldest images to make sure there is always enough free space for new images.

While running on my rev1 B it consumes around 12% CPU / 4% ram and manages to capture a full size image once ever 2-3 secs.

If you need to install PIL run "sudo aptitude install python-imaging-tk"