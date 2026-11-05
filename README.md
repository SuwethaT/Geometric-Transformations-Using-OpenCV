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

### Developed By:
**Name: Suwetha T

### Register No: 212225040446
### Program
1) Displaying Original Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found! Check the image filename.")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img.shape[:2]

print("Image Height:", h)

print("Image Width:", w)

plt.figure(figsize=(6, 6))

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.show()
---
2) Translated Image
---
import cv2

import numpy as np

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img.shape[:2]

M = np.float32([
    [1, 0, 100],
    [0, 1, 50]
])

translated = cv2.warpAffine(img, M, (w, h))

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1, 2, 2)

plt.imshow(translated)

plt.title("Translated Image")

plt.axis("off")

plt.show()
---
3) Scaled Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

scaled = cv2.resize(img, None, fx=1.5, fy=1.5)

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1, 2, 2)

plt.imshow(scaled)

plt.title("Scaled Image")

plt.axis("off")

plt.show()

print("Original Image Size:", img.shape)

print("Scaled Image Size:", scaled.shape)
---
4) Sheared Image
---
import cv2

import numpy as np

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img.shape[:2]

M = np.float32([
    [1, 0.3, 0],
    [0.2, 1, 0]
])

sheared = cv2.warpAffine(img, M, (w + 200, h + 200))

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1, 2, 2)

plt.imshow(sheared)

plt.title("Sheared Image")

plt.axis("off")

plt.show()
---
5) Reflected Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

reflected = cv2.flip(img, 1)

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1, 2, 2)

plt.imshow(reflected)

plt.title("Reflected Image")

plt.axis("off")

plt.show()
---
6) Rotated Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img.shape[:2]

center = (w // 2, h // 2)

M = cv2.getRotationMatrix2D(center, 45, 1)

rotated = cv2.warpAffine(img, M, (w, h))

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1, 2, 2)

plt.imshow(rotated)

plt.title("Rotated Image")

plt.axis("off")

plt.show()
---
7) Cropped Image
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread("dog.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

cropped = img[50:300, 50:300]

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)

plt.imshow(img)

plt.title("Original Image")

plt.axis("off")

plt.subplot(1, 2, 2)

plt.imshow(cropped)

plt.title("Cropped Image")

plt.axis("off")

plt.show()
---

##  Output
---

<img width="517" height="793" alt="image" src="https://github.com/user-attachments/assets/5168d996-bddb-4ab0-ba01-845e115d6e64" />

<img width="925" height="550" alt="image" src="https://github.com/user-attachments/assets/7de26ef7-cd63-434d-a341-17408ad9f2bc" />

<img width="892" height="552" alt="image" src="https://github.com/user-attachments/assets/a1a72bcf-fd67-4ed1-baf8-5470562e444f" />

<img width="932" height="517" alt="image" src="https://github.com/user-attachments/assets/828051f7-1ac4-40a6-83e1-01deab9ea9cf" />

<img width="881" height="515" alt="image" src="https://github.com/user-attachments/assets/d45fafa2-5643-4bbe-bb9c-44e3aaf082dd" />

<img width="926" height="537" alt="image" src="https://github.com/user-attachments/assets/f69d1ce9-68a3-401d-a2e9-71523a45166c" />

<img width="897" height="492" alt="image" src="https://github.com/user-attachments/assets/947fe3d0-a5fa-40d0-b10d-98ba5ce24c5f" />
---

### Image Translation
- Original image is displayed  
- Translated image (shifted right and down) is displayed  

### Image Scaling
- Original image is displayed  
- Downscaled image (0.5×) is displayed  
- Upscaled image (2×) is displayed  

### Image Shearing
- Original image is displayed  
- Horizontally sheared image is displayed  
- Vertically sheared image is displayed  

### Image Reflection
- Original image is displayed  
- Horizontally flipped image is displayed  
- Vertically flipped image is displayed  
- Both-axis flipped image is displayed  

### Image Rotation
- Original image is displayed  
- 45° rotated image is displayed  
- 90° rotated image is displayed  

---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
