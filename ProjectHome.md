Realtime Video Capture Toolkit is a project aims to make library and applications for video capture and processing.

Capture:

  * V4L2 API
    1. Query and set video device properties that include: Resolution, Image Format, Channel, Norm, fps...
    1. Read/Write and Memory mapped streaming I/O
  * YUYV/YUV420 to RGB/BGR conversion.

Processing
  * Utility to convert video frame to IplImage format for use with OpenCV.

UI
  * A simple GTK+ dialog to choose the video device to open and set the properties.

Demo application
  * Face Detection (based on the sample code from OpenCV project)

Click GettingStartedGuide for instructions to use the software.

![http://benlau.e-fever.org/modules/xcgal/albums/userpics/10001/normal_Screenshot-ConnectTo.png](http://benlau.e-fever.org/modules/xcgal/albums/userpics/10001/normal_Screenshot-ConnectTo.png)

Dialog to query the V4L2 device available and choose the one to open.

![http://benlau.e-fever.org/modules/xcgal/albums/userpics/10001/Screenshot-Video%20Tuning.png](http://benlau.e-fever.org/modules/xcgal/albums/userpics/10001/Screenshot-Video%20Tuning.png)

Adjust device properties

![http://benlau.e-fever.org/modules/xcgal/albums/userpics/10001/normal_facedetect.png](http://benlau.e-fever.org/modules/xcgal/albums/userpics/10001/normal_facedetect.png)

Sample program - facedetect from OpenCV

Source code : https://launchpad.net/rvtk/trunk