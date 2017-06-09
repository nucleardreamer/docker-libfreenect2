# dockerized libfreenect2
From source of the [libfreenect2](https://github.com/OpenKinect/libfreenect2) repo

## build
```
docker build -t nucleardreamer/libfreenect2 .
```

## running
If you want to run the test, you will need to expose your X server socket

```
xhost +local:root
docker run -it --privileged \
  -e DISPLAY=:0 \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --device /dev/bus/usb:/dev/bus/usb \
  nucleardreamer/libfreenect2 kinect_test
```
