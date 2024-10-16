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

### Developed By: sarvesh s
### Register No.: 212222230135
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the image

image = cv2.imread('doll.png')

# Convert to grayscale

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()

# Global thresholding
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()

# Adaptive thresholding (Gaussian)
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()

# Otsu's thresholding
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
## Output

### Original Image

![image](https://github.com/user-attachments/assets/73501332-0ad3-49a6-9ae7-142f89de9d8b)


### Global Thresholding


![image](https://github.com/user-attachments/assets/ec5d3271-97db-490b-9f92-770bff2df86f)

### Adaptive Thresholding

![image](https://github.com/user-attachments/assets/8ecf0294-4f19-47f9-ac68-a1fb614445f7)


### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/user-attachments/assets/e1eadac5-aa05-40df-9995-e634e41f9bf0)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
