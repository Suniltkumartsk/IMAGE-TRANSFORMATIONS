# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required libraries and images for the experiment

### Step2:
Translate the image using wrapAffine and the same can be used for Shearing the image

### Step3:
Use cv2.resize() to scale the image

### Step4:
use cv2.flip(img,2) to get the reflected image

### Step5:
Crop the image by using slicing

## Program:

### Developed By: SUNIL KUMAR T
### Register Number:212223240164
i)Image Translation
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('rdr2.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 
plt.imshow(image_rgb)
plt.title("Original Image")

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
ii) Image Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
iii)Image shearing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
iv)Image Reflection
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')

```
v)Image Rotation
```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
vi)Image Cropping
```
cropped_image = image_rgb[400:2000, 800:2100]  
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show() 
```
## Output:
### original Image:
![rdr2](https://github.com/user-attachments/assets/32abeba6-d8ba-4f0d-926f-e19c1e5f81af)


### i)Image Translation
![Screenshot 2025-04-23 202150](https://github.com/user-attachments/assets/7ba94371-de59-4484-812e-aa1d33340ce4)


### ii) Image Scaling
![Screenshot 2025-04-23 202221](https://github.com/user-attachments/assets/6536f967-8613-45c7-8541-2af10406dd56)


### iii)Image shearing
![Screenshot 2025-04-23 202327](https://github.com/user-attachments/assets/de035540-5266-4712-82a0-a9d7b3e7c60e)


### iv)Image Reflection
![Screenshot 2025-04-23 202336](https://github.com/user-attachments/assets/1cfd80aa-875f-45c3-9bc1-3dc093797635)


### v)Image Rotation
![Screenshot 2025-04-23 202346](https://github.com/user-attachments/assets/bb0d5fb1-19d7-401f-9b7c-fabd17ef284e)


### vi)Image Cropping
![Screenshot 2025-04-23 202355](https://github.com/user-attachments/assets/bae478c0-b323-4be6-8518-7faf69d8fb75)


## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
