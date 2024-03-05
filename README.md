# rtsp
for streaming video with 5 seconds delay:

sudo ffmpeg -f v4l2 -input_format mjpeg -video_size 640x480 -framerate 30 -i /dev/video0 -c:v libx264 -preset ultrafast -tune zerolatency -crf 22 -g 60 -keyint_min 60 -sc_threshold 0 -hls_time 0.01 -hls_list_size 5 -hls_wrap 10 ~/WS/robotics/vr_terminal/aframe_stuff/rtsp/stream.m3u8

to access in browser:
pyton3 -m http.server
