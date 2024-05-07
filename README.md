
# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.

## Program
### Developed By : PREM KUMAR K
### Register Number : 212222230111
```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('lap.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('lap.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output

### Original Image
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/2193c58b-7590-4257-9faa-deb5d9f44fb1)


### Global Thresholding
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/dac7222d-3591-428a-8d25-754294ff11ca)
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/5d662b59-66a9-4e22-8d96-0e678154afca)
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/4c3cc435-aad1-470a-83cc-161a4def909e)
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/590aeb73-54d7-4a01-8188-39c7854bfea8)
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/6621bfc6-73dc-4c3c-8055-cfab332b9d32)


### Adaptive Thresholding
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/850061f6-7476-4f34-8de2-f238ba211b05)
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/dbaf4b04-0a89-4710-b163-d129f4b641ef)

### Optimum Global Thesholding using Otsu's Method
![download](https://github.com/Sabariakash22009103/Thresholdingg/assets/119390227/c33511c1-7178-4c7c-b3b3-4b8cfe23cad7)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
