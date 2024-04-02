# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the image

### Step2:
Convert the input image to gray to get more details

### Step3:
Apply any smoothing filter, here we apply Gaussian blur

### Step4:
Apply an edge detector

### Step5:
Apply hough transform and show the detected edge on the original image


## Program:
```Python
Developed By: ANU VARSHINI M B
Register No: 212223240010

# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('catt.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('origianl',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()



```
## Output

### Input image and grayscale image
![gray](https://github.com/JEEVAABI/EDGE--LINKING-HOUGH-TRANSFORM/assets/93427098/439083fb-e2a7-40b9-ae23-c2168c8e8440)


### Canny Edge detector output
![canny](https://github.com/JEEVAABI/EDGE--LINKING-HOUGH-TRANSFORM/assets/93427098/ec7e0880-d7fa-446b-ae52-7e7e0bce53c0)



### Display the result of the Hough transform
![det](https://github.com/JEEVAABI/EDGE--LINKING-HOUGH-TRANSFORM/assets/93427098/5744c6ec-2e49-4f6a-aeb8-6d66e47b3931)




## Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform. 
