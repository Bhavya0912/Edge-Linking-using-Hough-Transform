# Edge-Linking-using-Hough-Transform
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
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('birdg.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)
# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()
# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)
# Display the result
plt.imshow(edges1)
```
## Output

### Input image and grayscale image

![image](https://user-images.githubusercontent.com/75235293/168869649-81a51f57-abb4-44a2-b6fa-fa0cba9ef38b.png)



### Canny Edge detector output

![image](https://user-images.githubusercontent.com/75235293/168869775-4f18a486-75bc-4339-a21d-84a04a0346f1.png)



### Display the result of Hough transform

![image](https://user-images.githubusercontent.com/75235293/168869866-f5d50e52-8cff-4029-b6c6-2632ae28e361.png)



## Result:
Thus the program is executed to detect lines using Hough transform.  
