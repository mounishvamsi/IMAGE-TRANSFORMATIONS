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
image=cv2.imread("Image1.jpg")
image.shape
#Display the images.
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()
```
## Output:

<img width="542" height="560" alt="image" src="https://github.com/user-attachments/assets/8db58ba3-e2bd-40d3-8e49-a1583fd56bea" />

## i)Image Translation
```
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```
## Output:

<img width="751" height="469" alt="image" src="https://github.com/user-attachments/assets/35825bdd-65be-4872-a932-c9c7f2eb67b9" />

## ii) Image Scaling
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  # Set title
plt.axis('off')
```
## Output:

<img width="662" height="328" alt="image" src="https://github.com/user-attachments/assets/8af870ec-58da-4bcb-b813-c74b25e82d48" />


## iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  
plt.title("Sheared Image")  
plt.axis('off')
```
## Output:
<img width="522" height="531" alt="image" src="https://github.com/user-attachments/assets/70054bb9-97aa-41b3-9683-3b69684b7a00" />


## iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image")  
plt.axis('off')
```
## Output:

<img width="477" height="519" alt="image" src="https://github.com/user-attachments/assets/3e83b557-2ef8-4e1d-9dea-5cb8de68b4c9"/>




## v)Image Rotation
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
## Output:

<img width="521" height="527" alt="image" src="https://github.com/user-attachments/assets/1db26cf2-9ad8-4d37-8ea6-53131c9dcd59" />


## vi)Image Cropping
```
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output:

<img width="669" height="524" alt="image" src="https://github.com/user-attachments/assets/71a33d9a-eaa5-4119-88f4-cb1743119e0c" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
