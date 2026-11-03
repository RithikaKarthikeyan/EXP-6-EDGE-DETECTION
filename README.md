# EXP-6-EDGE-DETECTION

## EDGE-DETECTION
### Aim
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

### Software Required
Anaconda - Python 3.7
OpenCV
NumPy
Matplotlib
### Algorithm
- Step 1
Import all the necessary modules for the program.

- Step 2
Load an image using the cv2.imread() function.

- Step 3
Convert the image into grayscale using cv2.cvtColor().

- Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

- Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

- Step 6
Use the Canny operator to detect edges in the image.

- Step 7
Display the edge-detected images using Matplotlib.

### Program
#### Developed By: RITHIKA K

#### Register Number: 212225040343
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sv.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```  
### Output
Input Image

<img width="385" height="446" alt="image" src="https://github.com/user-attachments/assets/2d9107c5-522c-40b3-a054-d8b87204c864" />

1. Sobel Edge Detector
   
<img width="425" height="457" alt="image" src="https://github.com/user-attachments/assets/5fe3f7ef-e84d-4c08-bc08-d169cc214f6c" />

2. Laplacian Edge Detector
   
<img width="457" height="446" alt="image" src="https://github.com/user-attachments/assets/7a2921c1-46bc-4a72-9f5c-a959bbce4cbd" />

3. Canny Edge Detector
   
<img width="382" height="442" alt="image" src="https://github.com/user-attachments/assets/4d7fa88d-1083-42bc-8e27-0b1787cfa5eb" />

### Result
Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.
