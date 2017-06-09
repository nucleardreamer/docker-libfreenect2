# dockerized libfreenect2
From source of the [libfreenect2](https://github.com/OpenKinect/libfreenect2) repo

## build

This will build with the latest git commit

```
docker build -t nucleardreamer/libfreenect2 .
```

To build with a specific release tag, use the `TAG` build argument

```
docker build --build-arg TAG=v0.2.0 -t nucleardreamer/libfreenect2:0.2.0 .
```

## running
If you want to run the test, you will need to expose your X server socket

```
xhost +local:root
docker run -it \
  -e DISPLAY=:0 \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --device /dev/bus/usb:/dev/bus/usb \
  nucleardreamer/libfreenect2 kinect_test
```
