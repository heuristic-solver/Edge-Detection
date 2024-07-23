# Corner Detection using OpenCV
This repository contains a simple implementation of corner detection in an image using OpenCV's goodFeaturesToTrack function. The code reads an image, converts it to grayscale, and then identifies corners in the image. Detected corners are marked with rectangles.

# Installation
To run this code, you need to have Python installed along with the OpenCV library. You can install OpenCV using pip.
  pip install opencv-python

# Code Explanation
  import cv2
  import numpy as np 


  img = cv2.imread('joel.jpg')

  gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)


  corners = cv2.goodFeaturesToTrack(gray, 100, 0.01, 150)


  for corner in corners:
      x, y = corners[0]
      x = int(x)
      y = int(y)
      cv2.rectangle(img, (x-10, y-10), (x+10, y+10), (0,255,0),2)

  cv2.imshow('corners found', img)
  cv2.waitKey()
  cv2.destroyAllWindows()
