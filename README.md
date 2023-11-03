# Image-Acquisition-from-Web-Cameraa
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera 

### Step 2:
Use cv2.imread to read the video or image 

### Step 3:
Use cv2.imwrite to save the image 

### Step 4:
Use cv2.imshow to show the video 

### Step 5:
End the program and close the output video window by pressing 'q'. 

## Program:
```
### Developed By: Thirukaalathessvarar S
### Register No:212222230161

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("captured_image.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('Live Video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![dip2_exp2](https://github.com/Thirukaalathessvarar-S/Image-Acquisition-from-Web-Cameraa/assets/121166390/8e1f90b4-71c1-4098-915d-9eaecdc7a83a)



### ii) Display the video
![dip1_exp2](https://github.com/Thirukaalathessvarar-S/Image-Acquisition-from-Web-Cameraa/assets/121166390/991e9d33-c8af-46af-8c89-d0dbf0a0c8ee)



### iii) Display the video by resizing the window
![dip3_exp2](https://github.com/Thirukaalathessvarar-S/Image-Acquisition-from-Web-Cameraa/assets/121166390/a7754e5c-27f8-4aa0-ae8b-2e5b9a83f0b7)

### iv) Rotate and display the video
![dip4_exp2](https://github.com/Thirukaalathessvarar-S/Image-Acquisition-from-Web-Cameraa/assets/121166390/107d0630-88af-4a57-9fb3-1cef73ff0546)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
