# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

- **Name:** Chowla Chaithanya
- **Register No:** 2305002004

---

##  Output

### Smoothing Filters
```

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("taj.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()

```
<img width="469" height="208" alt="{48B852CB-AE3D-4758-BA95-6F1EBFF1335F}" src="https://github.com/user-attachments/assets/7ce090be-ca11-4428-95f8-21a192f61134" />

ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="529" height="396" alt="{BA779E20-684B-47D5-A828-5DF23AD3BFD4}" src="https://github.com/user-attachments/assets/b1599224-9480-4a8b-90d6-bd551a839eb4" />

iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
<img width="537" height="417" alt="{5E262608-D805-4942-A1AA-9B6725D02EE5}" src="https://github.com/user-attachments/assets/0d09e793-8fd9-4adc-adf9-f245d52108a9" />

iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis("off")
plt.show()

```
<img width="558" height="432" alt="{42E20BD9-1D7F-466B-A582-24AAE81B9DDF}" src="https://github.com/user-attachments/assets/bcc9da9c-6f5e-4753-bf8b-4f6a64d3c260" />

###  Sharpening Filters
i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
<img width="549" height="425" alt="{EC6D2C00-40E0-4497-BA41-882A9409483B}" src="https://github.com/user-attachments/assets/64854d72-d81a-451e-8278-57e978bce9da" />

ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
<img width="543" height="428" alt="{670B9D64-CCA3-4897-B262-613873506BE2}" src="https://github.com/user-attachments/assets/f0438131-cad4-44db-a40d-a276e58923bd" />

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
