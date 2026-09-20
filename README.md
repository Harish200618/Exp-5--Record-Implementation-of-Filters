# Ex.No:5 Implementation of filter
# Name: Harish S
# Register No: 212224240052

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

  
  ```
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  ```
  img = cv2.imread("lion.png")
  img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
  ```
  ```
  plt.imshow(img)
  plt.title("Original Image")
  plt.axis("off")
  plt.show()
  ```
  1. Averaging Filter
  ```
  avg = cv2.blur(img, (5,5))
  plt.imshow(avg)
  plt.title("Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
  2. Weighted Averaging Filter
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
3. Gaussian Filter
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()
```
4. Median Filter
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
5. Laplacian Sharpening (Kernel)
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
6. Laplacian Operator
```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

### Smoothing Filters

- Original Image 
<img width="389" height="389" alt="download" src="https://github.com/user-attachments/assets/3391b31f-a782-451f-b419-ba85c216fcaa" />



- Weighted averaging provides smoother result with less distortion

<img width="717" height="359" alt="download" src="https://github.com/user-attachments/assets/0437563e-ccd4-4c72-8b0a-b2d41be87f22" />


 
- Gaussian filter preserves edges better while reducing noise

<img width="717" height="359" alt="download" src="https://github.com/user-attachments/assets/a9ff90aa-a2e2-45d0-b1a4-7dc162cc307d" />



- Median filter removes salt-and-pepper noise effectively

<img width="717" height="359" alt="download" src="https://github.com/user-attachments/assets/deeacf85-e2a5-43c2-bf9f-be12184570ad" />




###  Sharpening Filters




<img width="717" height="359" alt="download" src="https://github.com/user-attachments/assets/9981541f-f14a-4a42-bc15-5e4be0ca2cfc" />

###  Using Laplacian Operator

<img width="1408" height="441" alt="image" src="https://github.com/user-attachments/assets/8ac84f83-c3c6-43b6-afca-fd45384e3683" />



---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
