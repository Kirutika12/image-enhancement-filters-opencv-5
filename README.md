# Image-enhancement-filters-opencv-5
## Aim
To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

## The program performs the following operations:
Read and display an input image
Apply Averaging filter
Apply Weighted Averaging filter
Apply Gaussian filter
Apply Median filter
Apply Laplacian sharpening using kernel
Apply Laplacian operator
Display all outputs for comparison
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm
### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., image.jpg).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using cv2.blur().

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

### Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

### Step 7:
Apply Median Filter using cv2.medianBlur().

### Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

### Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

### Step 10:
Display all filtered images using a grid layout for comparison.

## Program:
### Developed By
### Name: Kirutika K R
### Register No: 212224230128
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("rose.png")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
plt.show()
```
### 1.Averaging Filter:
```
avg = cv2.blur(img, (5,5))
plt.imshow(avg)
plt.title("Averaging Filter")
plt.axis("off")
plt.show()
```
### 2.Weighted Averaging Filter:
```
kernel = np.array([[1,2,1],
                 [2,4,2],
                 [1,2,1]], np.float32) / 16
weighted = cv2.filter2D(img, -1, kernel)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()
```
### 3.Gaussian Filter:
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()
```
### 4.Median Filter:
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
### 5.Laplacian Sharpening (Kernel):
```
kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
### 6.Laplacian Operator

```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
## Output
### original image:
<img width="633" height="512" alt="image" src="https://github.com/user-attachments/assets/68d38fd3-74eb-463c-a9cc-857ea0f68e62" />

### Averaging filter:
<img width="626" height="507" alt="image" src="https://github.com/user-attachments/assets/cf4e179c-82fa-47a2-a9c0-33ce14020910" />

### weighted Averaging filter:
<img width="610" height="507" alt="image" src="https://github.com/user-attachments/assets/21bb8d97-a8ac-4129-b49e-f5ff7bc65c46" />

### Gaussian filter:
<img width="615" height="511" alt="image" src="https://github.com/user-attachments/assets/2048fcc7-f710-461f-90fe-f1ea5fa9365f" />

### Media filter:
<img width="602" height="502" alt="image" src="https://github.com/user-attachments/assets/e0f39678-57f7-4321-9dfe-2b031cbffd88" />

### laplacian kernel:
<img width="607" height="502" alt="image" src="https://github.com/user-attachments/assets/01356c09-2e9e-4a0d-8b79-eb61860c11be" />

### laplacian operator:
<img width="621" height="510" alt="image" src="https://github.com/user-attachments/assets/8cb64843-53af-41bb-bd24-e5e2c5183e1c" />

## Result
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
