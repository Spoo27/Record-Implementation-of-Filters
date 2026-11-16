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

## Name: Spoorthi V
## Register No: 212224230271

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("Qno. 1.jpeg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img)
plt.title("Original Image")
plt.axis("off")
plt.show()

avg = cv2.blur(img, (5,5))
plt.imshow(avg)
plt.title("Averaging Filter")
plt.axis("off")
plt.show()

kernel = np.array([[1,2,1],
                 [2,4,2],
                 [1,2,1]], np.float32) / 16
weighted = cv2.filter2D(img, -1, kernel)
plt.imshow(weighted)
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()

gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()

median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()

kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
##  Output
<img width="587" height="452" alt="image" src="https://github.com/user-attachments/assets/a9396088-f50e-4d5e-b0ab-dd208e4e1c21" />
<img width="572" height="451" alt="image" src="https://github.com/user-attachments/assets/2b4f527d-e29d-4867-beac-df972287a2b7" />
<img width="563" height="447" alt="image" src="https://github.com/user-attachments/assets/b789d36b-23e9-4ee9-9fa3-16687d94ab60" />
<img width="580" height="453" alt="image" src="https://github.com/user-attachments/assets/ec74d7e4-6a8a-48ef-9a17-dc560ecc462d" />
]<img width="586" height="441" alt="image" src="https://github.com/user-attachments/assets/8f463acf-1b63-4cdb-9cfe-cd84397dcfc9" />
<img width="562" height="450" alt="image" src="https://github.com/user-attachments/assets/ff2676d6-a2c8-432d-add0-f656282e2b5f" />
<img width="577" height="448" alt="image" src="https://github.com/user-attachments/assets/ca333a1a-980e-4405-be58-cf5296033906" />

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
