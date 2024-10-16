# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread('HappyFish.jpg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()



# Use Global thresholding to segment the image
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()




# Use Adaptive thresholding to segment the image
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()



# Use Otsu's method to segment the image 
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()

```
## Output

### Original Image
<br>
<br>
<img width="519" alt="Screenshot 2024-10-16 at 5 29 40 PM" src="https://github.com/user-attachments/assets/0f4ab3d7-ff77-4068-a427-a117b660e9eb">

<br>
<br>
<br>

### Global Thresholding
<br>
<br>
<img width="538" alt="Screenshot 2024-10-16 at 5 31 51 PM" src="https://github.com/user-attachments/assets/9e845b46-14b0-4f27-933b-214a0c09b034">


<br>
<br>
<br>

### Adaptive Thresholding
<br>
<br>
<img width="514" alt="Screenshot 2024-10-16 at 5 30 16 PM" src="https://github.com/user-attachments/assets/c553039f-10d7-4467-a50a-6f9c9097d896">

<br>
<br>
<br>

### Optimum Global Thesholding using Otsu's Method
<br>
<br>
<img width="519" alt="Screenshot 2024-10-16 at 5 31 16 PM" src="https://github.com/user-attachments/assets/efc37de8-859c-4653-9a35-63358e32737c">
<br>
<br>
<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
