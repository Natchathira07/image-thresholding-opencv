# EXP-8 Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
  
- Adaptive Thresholding
  
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
  
- Jupyter Notebook / VS Code
  
- OpenCV (cv2)
  
- NumPy
  
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
  
- Apply thresholding to separate foreground and background pixels.
  
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
  
- Apply Adaptive Mean Thresholding.
  
- Apply Adaptive Gaussian Thresholding.
  
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value
  
- Apply Otsu's thresholding technique.
  
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program

## Developed By

### Name:VD Natchathira
### Register No:212224230178
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
image = cv2.imread("C:/Users/admin/Pictures/Screenshots/Screenshot 2026-08-26 170701.png")  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```
```
plt.subplot(2, 1, 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```
```
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```
```
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

```
```
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
```
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

### Original Grayscale Image

<img width="436" height="472" alt="image" src="https://github.com/user-attachments/assets/e6d60f04-d766-415c-a55e-996b8260196f" />

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

### Global Thresholding

<img width="217" height="220" alt="image" src="https://github.com/user-attachments/assets/afefd0c4-d718-4bf2-b3f3-35cc8fb6be52" />

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

### Adaptive Thresholding

r<img width="213" height="220" alt="image" src="https://github.com/user-attachments/assets/db3b7c57-956f-4f4f-b85a-a348dd57a073" />

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.

### Otsu's Thresholding

<img width="220" height="216" alt="image" src="https://github.com/user-attachments/assets/1b29babc-40be-40c3-a9cd-510dfeb93d4b" />

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.


## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
