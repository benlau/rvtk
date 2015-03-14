#summary Getting Started

# Details #

The source comes with two libraries. They are librvtk-vc and librvtk-opencv. librvtk-vc is the core library to deal with video capture device(V4l2 API). librvtk-opencv is “supposed” to be an extension to OpenCV for access low level device setting, but only few functions are implemented and the design is not well. It will be completely rewritten afterward. All features that should not be provided by librvtk-vc will be there (e.g. GTK+ Dialog)

librvtk-vc itself is a very simple library that just requires standard library like libc6-dev in order to build, but librvtk-opencv demands heavier packages like gtk+-2.0 and OpenCV.

The package of OpenCV has been available in Debian Etch/SID, they could be installed by:

```
apt-get install libcv-dev libcvaux-dev libhighgui-dev
```

The source code is held by Bazaar , a distributed version control system , instead of the Subversion system provided by Google Code. You must have Bazaar be installed in order to retrieve the source code. The packages should be available for most distribution :  http://bazaar-vcs.org/Download

The build instructions:

```

bzr branch https://code.launchpad.net/~benlau/rvtk/trunk rvtk

cd rvtk
./autogen.sh --prefix=/tmp/usr # for testing
make
make install

```

Build Debian package
```
cd rvtk
./autogen.sh
make docs  #pre-build the document. It may report error when making gtk document. Simply ignore it.
dpkg-buildpackage -rfakeroot -us -uc -i\.bzr
```

There are two demo applications available. The first one is a video viewer with two dialogs to choose the input video device and set the properties respectively. The other one is a face detection program from the sample code of OpenCV project.

```
    /tmp/usr/bin/v4l2-demo
    /tmp/usr/bin/facedetect
```

![http://rvtk.googlecode.com/svn/wiki/images/Screenshot-facedetect.png](http://rvtk.googlecode.com/svn/wiki/images/Screenshot-facedetect.png)

The library is still under development. The API may change for new version. Therefore, only static link libraries are provided.

API Doc:
  * http://benlau.e-fever.org/projects/docs/rvtk/index.html

Tested Devices :

  * KWorld DVD Marker (em28xx)
  * Pinnacle DVC 90 (em28xx)
  * A 4-input unbanded capture card (bttv) - Burst must be turnned on in order to get 25fps
  * Logitech Quickcam Pro 4000 (PWC) -  The PWC do not support to adjust FPS by standard V4L2 API
  * Logitech Quickcam Pro for Notebooks(UVC) - The driver supports MJPEG and YUYV for output. If chosen YUYV, only 1024×576 is provided.