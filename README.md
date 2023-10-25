# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1 : Read the image

Step2 : Convert the input image to gray to get more details

Step3 : Apply any smoothing filter, here we apply Gaussian blur

Step4 : Apply an edge detector

Step5 : Apply hough transform and show the detected edge on the original image

## Program:
```
Developed by: G Lutheesh
Reg. No.: 212221230029
```
```

# Read image and convert it to grayscale image




# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('exp_8.png',-1)
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

![WhatsApp Image 2023-10-25 at 10 54 13_bfde2fc6](https://github.com/Lutheeshgoparapu/EDGE--LINKING-HOUGH-TRANSFORM/assets/94154531/93b596c5-5ada-49e5-8d37-5834471d777f)

![WhatsApp Image 2023-10-25 at 10 54 25_fee0e6dd](https://github.com/Lutheeshgoparapu/EDGE--LINKING-HOUGH-TRANSFORM/assets/94154531/2d31461d-1fcf-436b-8e94-1a4e4e025ee3)



### Canny Edge detector output

![WhatsApp Image 2023-10-25 at 10 54 38_5b52c68c](https://github.com/Lutheeshgoparapu/EDGE--LINKING-HOUGH-TRANSFORM/assets/94154531/5f829602-1b2f-4a1e-88e1-b04f98c7f19f)




### Display the result of Hough transform


![WhatsApp Image 2023-10-25 at 10 54 53_dc62c8cc](https://github.com/Lutheeshgoparapu/EDGE--LINKING-HOUGH-TRANSFORM/assets/94154531/2c9d981f-4f0a-4f41-8549-15090f1bc998)





## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
