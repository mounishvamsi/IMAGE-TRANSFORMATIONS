# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step 1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

## Step 2:
Read the input image using cv2.imread() and store it in a variable for further processing

## Step 3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

## Step 4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

## Program:
```python
Developed By:R.Mounish Vamsi Kumar
Register Number:212224240096
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 1: Load the image
image = cv2.imread('Qn4.jpg')  # Load the image from file
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 
```
## Output:
<img width="671" height="480" alt="image" src="https://github.com/user-attachments/assets/90018ecb-769a-4ce9-b5fd-b7ea06d8a20c" />

## i)Image Translation
```
# Step 2: Image Translation
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('off')
```
## Output:

<img width="674" height="489" alt="image" src="https://github.com/user-attachments/assets/9844e123-dc71-4a9d-8842-aefdc08369f6" />

## ii) Image Scaling
```
# Step 3: Image Scaling
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
## Output:

<img width="696" height="219" alt="image" src="https://github.com/user-attachments/assets/83266916-d50b-4375-bf4a-ee0ac5ae2508" />



## iii)Image shearing
```
# Step 4: Image Shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')

```
## Output:
<img width="722" height="483" alt="image" src="https://github.com/user-attachments/assets/07d2ccf1-99d1-479a-9a06-d753caedc091" />

## iv)Image Reflection
```
# Step 5: Image Reflection
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')
```
## Output:
<img width="670" height="493" alt="image" src="https://github.com/user-attachments/assets/6e10bf5f-9d58-479b-9ff3-2b1c7ad2f484" />





## v)Image Rotation
```
# Step 6: Image Rotation
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')

```
## Output:
<img width="517" height="507" alt="image" src="https://github.com/user-attachments/assets/dd6450ea-6d59-4562-b57a-6291de8f709f" />




## vi)Image Cropping
```
# Step 7: Image Cropping
x, y, w, h = 100, 100, 200, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
## Output:
<img width="660" height="517" alt="image" src="https://github.com/user-attachments/assets/fc1c036f-da7d-496c-b481-a33222df633e" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
