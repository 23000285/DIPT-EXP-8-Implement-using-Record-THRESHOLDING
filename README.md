# EXP-8 IMAGE SEGMENTATION USING THRESHOLDING TECHNIQUES IN OPENCV

**Name:** VENKATANATHAN P R  
**Register No:** 212223240173

---

## Aim

To segment an image using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

---

# Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('cricket.jpg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale


# Original Image
plt.subplot(2, 2, 1)
plt.imshow(
    cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
)  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')


# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(
    gray_image,
    127,
    255,
    cv2.THRESH_BINARY
)


# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image,
    255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11,
    2
)


# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(
    gray_image,
    0,
    255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)


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
---

## Output

### Original Image

<img width="769" height="238" alt="image" src="https://github.com/user-attachments/assets/74d10eff-018d-4afb-aa47-6c3977aaf12c" />


### Global Thresholding

<img width="500" height="253" alt="image" src="https://github.com/user-attachments/assets/3c7a6120-c48d-438b-bd77-8cee8e90a148" />


### Adaptive Thresholding

<img width="376" height="235" alt="image" src="https://github.com/user-attachments/assets/79ecb264-e4c8-4475-82c3-4a2a11362842" />


### Otsu's Thresholding

<img width="374" height="241" alt="image" src="https://github.com/user-attachments/assets/cb5593aa-7524-417a-8ebc-1e7e8cb7424f" />


### Comparison Output

<img width="828" height="496" alt="image" src="https://github.com/user-attachments/assets/c47dab72-b5d2-4b90-8f74-9098f63f0c14" />


---

## Comparison of Thresholding Techniques

| Technique | Threshold Selection | Main Characteristic |
|---|---|---|
| Global Thresholding | Fixed value (`127`) | Uses one threshold for the complete image |
| Adaptive Thresholding | Local regions | Calculates threshold values for different regions |
| Otsu's Thresholding | Automatic | Automatically determines an optimal threshold |

---

## Result

Thus, image segmentation was successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV.

The three thresholding methods were applied to the grayscale image and their results were displayed and compared successfully.

---

## Developed By

**Name:** VENKATANATHAN P R  
**Register No:** 212223240173
