# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:

Read the input image using cv2.imread() and store it in a variable for further processing.


### Step3:

Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
```python
Developed By: Samakash R S
Register Number: 212223230182

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('dog.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  
plt.imshow(image_rgb)
plt.title("Orginal image")


i)Image Translation

# Image Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 30], [0, 1, 60]])  # Translate by (30, 60) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')


ii) Image Scaling

#Image Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')


iii)Image shearing

#Image shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')


iv)Image Reflection

#Image Reflection
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')


v)Image Rotation

#Image Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 90, 1)  # Rotate by 90 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')


vi)Image Cropping

#Image Cropping
cropped_image = image_rgb[5:150, 15:200]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()


```
## Output:

### Original Image

![alt text](<Screenshot 2025-03-29 141346.png>)
<br>

### i)Image Translation

![alt text](<Screenshot 2025-03-29 141353.png>)
<br>

### ii) Image Scaling

![alt text](<Screenshot 2025-03-29 141400.png>)
<br>


### iii)Image shearing

![alt text](<Screenshot 2025-03-29 141409.png>)
<br>


### iv)Image Reflection

![alt text](<Screenshot 2025-03-29 141418.png>)
<br>



### v)Image Rotation

![alt text](<Screenshot 2025-03-29 141426.png>)
<br>



### vi)Image Cropping

![alt text](<Screenshot 2025-03-29 141433.png>)
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
