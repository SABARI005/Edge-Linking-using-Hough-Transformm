# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:

### Developed by : SABARI S
### Register no : 212222240085
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('chess.png') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
## Output

![{83C5B839-2EFB-4755-B618-B9FCBDFB29E7}](https://github.com/user-attachments/assets/59a0535b-5bc0-4e0a-a3f6-4e4d28d2c82c)

## Grayscale Image:
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
## Output

![{1D5802F4-2DF6-4557-9241-EA1813A6FCCC}](https://github.com/user-attachments/assets/5d092b32-d5fa-49e3-a9a6-fcf007d34055)

## Canny Edge Detector:
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```
## Output

![{CA34D6F8-E062-44F3-BA25-ED1B6275687C}](https://github.com/user-attachments/assets/078b45a7-8512-454d-83c8-c80a94a48514)

## Detect lines using the probabilistic Hough transform
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
        plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
## Output

![{4CF5C913-5E32-4F34-9CA3-950689A48489}](https://github.com/user-attachments/assets/86ae62ed-ecad-4acd-b317-e9f4cd6d7c22)

# Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
