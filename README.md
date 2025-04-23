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
## Output
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('img_0.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/8fb3cf09-1c09-42c1-a6b6-ae94a486e97f)

### Input image and grayscale image

```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/835b3d1b-fc03-42be-8e92-a2dd94c4450d)

### Canny Edge detector output

```python
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/d3cd0536-8fac-4616-a2d3-0053bf8c1da2)

### Display the result of Hough transform

```python
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0] 
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 5)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/2bffba95-13dc-434a-afff-81bff47ff20a)
## Result:
 Thus, the lines in the image were successfully detected using the Hough Transform method in Python.
