# THRESHOLDING
## Name: Rishivarman R
## Reg No.: 212224100050
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1 :
Load the image and convert it to grayscale.

### Step2 :
Apply a single, fixed threshold value across the entire image.

### Step3 :
Calculate and apply a separate, local threshold for different small regions.

### Step4 :
Calculate and apply a separate, local threshold for different small regions.

### Step5 :
Show the original image and the three segmented (binary) results for comparison.

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('nature.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()



```
## Output

### Original Image
<img width="342" height="202" alt="image" src="https://github.com/user-attachments/assets/c2834094-133a-4a43-ada5-427904e1d0ee" />


### Global Thresholding

<img width="352" height="215" alt="image" src="https://github.com/user-attachments/assets/0b56f650-c888-4aec-a693-8c1c71f635ff" />

### Adaptive Thresholding
<img width="335" height="196" alt="image" src="https://github.com/user-attachments/assets/4bfd1e34-0929-441d-8c1f-e6f767b3708c" />

### Optimum Global Thesholding using Otsu's Method
<img width="308" height="191" alt="image" src="https://github.com/user-attachments/assets/ae71415e-e7f7-473a-ac0c-0a650224b31f" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
