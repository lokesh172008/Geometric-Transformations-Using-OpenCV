# Geometric Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('car.jpg') 

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off')
```
### Image Translation
```
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  

translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0])) 
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')

```

### Image Scaling
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')

```
### Image Shearing 
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')
```
### Image Reflection
```
reflected_image = cv2.flip(image, 2)  
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")  
plt.axis('off')
```
### Image Rotation
```
(height, width) = image.shape[:2] 
angle = 45  
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) 
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image") 
plt.axis('off')
```
###  Cropped image
```
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image") 
plt.axis('off')
```

### Developed By:
**Name:** _
K.Lokesh Achari
### Register No:
212225040208

---

##  Output

<img width="515" height="319" alt="download" src="https://github.com/user-attachments/assets/33a3526d-9626-4b37-b3f4-769a9e6ad604" />


<img width="515" height="319" alt="download" src="https://github.com/user-attachments/assets/d6cc7549-c35d-41d6-95e7-d848ed846ca0" />

<img width="515" height="151" alt="download" src="https://github.com/user-attachments/assets/62660a7a-a464-48a1-bdb1-e1fba39e151e" />
  
<img width="515" height="319" alt="download" src="https://github.com/user-attachments/assets/60f6de7a-4ea6-452d-9b69-0d9040aed73c" />

<img width="515" height="319" alt="download" src="https://github.com/user-attachments/assets/0898ff6a-12f4-423f-aa9f-86b0ee7f9a9f" />

<img width="515" height="319" alt="download" src="https://github.com/user-attachments/assets/fd266711-426a-4642-9596-7560fe6ed48b" />

<img width="512" height="409" alt="download" src="https://github.com/user-attachments/assets/c6c66f95-98b7-41d7-bd89-f9b354199439" />
   

---
   
   
##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
