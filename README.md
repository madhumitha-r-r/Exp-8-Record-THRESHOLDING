# Exp-8-Record-THRESHOLDING

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Algorithm

### Step 1: Import Libraries

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2: Read the Image and Convert to Grayscale

- Load the input image using OpenCV.
- Convert the input image into grayscale format.

### Step 3: Global Thresholding

- Apply global thresholding with a fixed threshold value of 127.
- Separate foreground and background pixels.

### Step 4: Adaptive Thresholding

- Apply Adaptive Gaussian Thresholding.
- Use a maximum value of 255.
- Set block size to 11 and constant value to 2.

### Step 5: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.

### Step 6: Display the Results

- Display the original image.
- Display the Global Thresholding output.
- Display the Adaptive Thresholding output.
- Display the Otsu's Thresholding output.

## Program

## Developed By

- **Name:** MADHUMITHA R R
- **Register No:** 212224240083

### Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2: Read the Image and Convert to Grayscale

```python
# Step 2: Read the image and convert to grayscale
image = cv2.imread('img.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```

### Step 3: Display the Original Image

```python
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
```

### Step 4: Global Thresholding

```python
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```

### Step 5: Adaptive Thresholding

```python
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```

### Step 6: Otsu's Thresholding

```python
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```

### Step 7: Display All Results

```python
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```

## Output

### 1. Original Image

<img width="117" height="135" alt="image" src="https://github.com/user-attachments/assets/4b25f86f-b3f6-45f9-a31c-a2abb47e202a" />


### 2. Global Thresholding

<img width="148" height="152" alt="image" src="https://github.com/user-attachments/assets/e86e0ec9-f57f-4834-a1c6-14aee39e77f6" />


### 3. Adaptive Thresholding

<img width="165" height="152" alt="image" src="https://github.com/user-attachments/assets/0dc23788-7d08-4837-b5b9-b574bf42b1e8" />


### 4. Otsu's Thresholding

<img width="115" height="150" alt="image" src="https://github.com/user-attachments/assets/2486e0cc-9826-441c-8034-c41c82ffcfaf" />


## Result

Thus, image segmentation was successfully performed using Global Thresholding, Adaptive Gaussian Thresholding, and Otsu's Thresholding techniques in OpenCV.

