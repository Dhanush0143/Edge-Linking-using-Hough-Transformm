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
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('imgme.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 13, 130)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)


plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')

```
## Output

### Input image and grayscale image

<img width="579" height="515" alt="Screenshot 2025-11-13 105902" src="https://github.com/user-attachments/assets/ef97239e-acbf-45e9-a1f5-669138bf9af8" />

<img width="493" height="498" alt="Screenshot 2025-11-13 105911" src="https://github.com/user-attachments/assets/6c8425ef-d706-4c35-90af-9e68f61f5f9a" />



### Canny Edge detector output

<img width="432" height="514" alt="Screenshot 2025-11-13 105921" src="https://github.com/user-attachments/assets/efa3a243-7339-4fb6-bf08-308aff3b3498" />


### Display the result of Hough transform
<img width="446" height="502" alt="Screenshot 2025-11-13 105954" src="https://github.com/user-attachments/assets/b491a9d2-5b2a-4063-bc90-9e71cffb2526" />


## Result:
Thus the code to perform Edge detection using Hough Transform was written and executed successfully.
