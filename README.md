# Edge-Detection
## AIM:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary modules.

### Step 2:
For performing edge detection on a image. 
- Sobel 
```python
sobelx=cv2.Sobel(gray,cv2.CV_64F,1,0,5)
sobely=cv2.Sobel(gray,cv2.CV_64F,0,1,5)
sobelxy=cv2.Sobel(gray,cv2.CV_64F,1,1,5)
```
- Laplacian
```python
lap=cv2.Laplacian(gray,cv2.CV_64F)
```
- Canny
```python
canny=cv2.Canny(gray,120,150)
```

### Step 3:
Display all the images with their respective edge detected images.

## PROGRAM:
```
/*
Developed by: A.Divya Meenakshi
Registration Number : 212220230014
*/
```

``` Python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image, Convert to grayscale and remove noise
image1=cv2.imread('flower.jpg',0)
plt.imshow(image1)

# SOBEL EDGE DETECTOR
sobelx = cv2.Sobel(image1,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(image1,cv2.CV_64F,0,1,ksize=5)
sobelxy= cv2.Sobel(image1,cv2.CV_64F,1,1,ksize=5)
plt.imshow(sobelx,cmap='gray')
plt.imshow(sobely,cmap='gray')
plt.imshow(sobelxy,cmap='gray')

# LAPLACIAN EDGE DETECTOR
dst = cv2.Laplacian(image1,cv2.CV_16S,ksize=3)
plt.imshow(dst,cmap='gray')
abs_dst = cv2.convertScaleAbs(dst)
plt.imshow(abs_dst,cmap='gray')
# CANNY EDGE DETECTOR

edges = cv2.Canny(image1,100,200)
plt.imshow(image1,cmap = 'gray')
plt.title('Original Image'), plt.xticks([]), plt.yticks([])
plt.imshow(edges,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()
```
## OUTPUT:
### SOBEL EDGE DETECTOR

![d1](https://user-images.githubusercontent.com/75235402/168738797-3f48e623-2dce-4659-baff-e2bde4b35bea.jpg)



### LAPLACIAN EDGE DETECTOR

![d2](https://user-images.githubusercontent.com/75235402/168738800-d220e373-b61c-4085-a460-4b7f6e779c50.jpg)




### CANNY EDGE DETECTOR

![d3](https://user-images.githubusercontent.com/75235402/168738807-480ea615-1093-4989-9a00-c01b669edca2.jpg)



## RESULT:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
