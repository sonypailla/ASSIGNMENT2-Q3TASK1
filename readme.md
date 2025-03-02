Task 1: Edge Detection Using Sobel Filters

Overview

This task demonstrates the application of Sobel filters to perform edge detection on a grayscale image. The Sobel filter is commonly used to highlight horizontal and vertical edges in an image.

Requirements

Python 3.x

Libraries:

OpenCV

NumPy

Matplotlib

Install the required libraries using:
pip install opencv-python numpy matplotlib
Task Description

Objective

Load a grayscale image.

Apply the Sobel filter in both x-direction (horizontal edges) and y-direction (vertical edges).

Display the original image and the edge-detected images using Sobel filters.

Implementation
# Task 1: Edge Detection Using Sobel Filters

## Overview
This task demonstrates the application of **Sobel filters** to perform edge detection on a grayscale image. The **Sobel filter** is commonly used to highlight horizontal and vertical edges in an image.

## Requirements
- Python 3.x
- Libraries:
  - OpenCV
  - NumPy
  - Matplotlib

Install the required libraries using:
```bash
pip install opencv-python numpy matplotlib
```

## Task Description
### Objective
1. **Load a grayscale image**.
2. **Apply the Sobel filter** in both **x-direction** (horizontal edges) and **y-direction** (vertical edges).
3. **Display the original image** and the edge-detected images using Sobel filters.

### Implementation
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Path to the grayscale image
image_path = r'C:\Users\paill\OneDrive\Pictures\Greyscale.jpg'  # Update the path as needed

# Load the image as grayscale
image = cv2.imread(image_path, cv2.IMREAD_GRAYSCALE)

# Check if the image was loaded successfully
if image is None:
    raise ValueError(f"Image at path {image_path} could not be loaded. Please check the path.")

# Apply Sobel filter in the x-direction (horizontal edges)
sobel_x = cv2.Sobel(image, cv2.CV_64F, 1, 0, ksize=3)

# Apply Sobel filter in the y-direction (vertical edges)
sobel_y = cv2.Sobel(image, cv2.CV_64F, 0, 1, ksize=3)

# Convert the results to uint8 for display
sobel_x_abs = cv2.convertScaleAbs(sobel_x)
sobel_y_abs = cv2.convertScaleAbs(sobel_y)

# Display the results
plt.figure(figsize=(10, 10))

plt.subplot(1, 3, 1)
plt.imshow(image, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(sobel_x_abs, cmap='gray')
plt.title('Edge Detection (Sobel-X)')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(sobel_y_abs, cmap='gray')
plt.title('Edge Detection (Sobel-Y)')
plt.axis('off')

plt.tight_layout()
plt.show()
```

### Explanation
- **Sobel-X Filter**: Detects horizontal edges.
- **Sobel-Y Filter**: Detects vertical edges.

## Usage
1. **Ensure the image file is in the correct path**.
2. **Run the script** to visualize the original and filtered images.
3. The output consists of:
   - **Original Image**
   - **Sobel-X Filtered Image** (Horizontal Edges)
   - **Sobel-Y Filtered Image** (Vertical Edges)

## Results
- The program will display three images:
  1. **Original Image**
  2. **Sobel-X Filtered Image**
  3. **Sobel-Y Filtered Image**


---
**Author**: Sony Pailla  
**Student ID**: [700765443]

