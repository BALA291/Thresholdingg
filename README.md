# EX-08 THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
- **Step1:** Load the necessary packages.

- **Step2:** Read the Image and convert to grayscale.

- **Step3:** Use Global thresholding to segment the image.

- **Step4:** Use Adaptive thresholding to segment the image.

- **Step5:** Use Otsu's method to segment the image and display the results.

## Program
```
NAME : BALAMURUGAN B
REG : 212222230016

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('cat.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('cat.jpeg.jpg',0)

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

![image](https://github.com/BALA291/Thresholdingg/assets/120717501/896a5060-0d4a-4627-b8b0-d7c994026727)

### Global Thresholding
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/1a03e9e5-b47c-4d5c-8ff1-eb5c4d8bb3ea)
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/3a0d534c-8a11-48f1-8655-4866b7587c54)
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/d8a2c8cb-2c33-4e50-bed8-d78fb3a63f86)
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/c65b8a57-b438-4522-a1d1-6a20e36b93c6)
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/dffff962-4142-4c08-abf8-d13db895829f)


### Adaptive Thresholding
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/a5829b2f-2ae8-4ccf-91e9-5859f1231a66)
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/347cb803-cc31-4272-af0b-c2cad83c57bc)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/BALA291/Thresholdingg/assets/120717501/962144c1-fd6a-4b60-bdc7-bda5b413236d)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
