# Implement-Opening-and-Closing-using-Python-and-OpenCV
## Aim

To implement Morphological Opening and Closing operations using Python and OpenCV on a text image and visualize the output using Matplotlib.

## Algorithm
## Opening Operation
- Import required libraries such as OpenCV, NumPy, and Matplotlib.
- Create a blank black image using NumPy.
- Add text to the image using cv2.putText().
- Create a structuring element (kernel) of size 3 × 3.
- Apply Morphological Opening using cv2.morphologyEx() with cv2.MORPH_OPEN.
- Convert the images from BGR to RGB format for display.
- Display the original and opened images using Matplotlib.
## Closing Operation
- Use the same input image and kernel.
- Apply Morphological Closing using cv2.morphologyEx() with cv2.MORPH_CLOSE.
- Convert the output image from BGR to RGB format.
- Display the original and closed images using Matplotlib.
## Program
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Harini', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)
# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Closed Operation")
plt.axis('off')
```

## Output

## Image with text

<img width="414" height="331" alt="image" src="https://github.com/user-attachments/assets/49305263-5728-447e-9905-e2691a554aac" />

## Open operation

<img width="413" height="329" alt="image" src="https://github.com/user-attachments/assets/4f292f93-0508-4cef-bfe4-93bfe5f32a7b" />

## Closed operation

<img width="408" height="337" alt="image" src="https://github.com/user-attachments/assets/bedcf0ee-4b89-4847-a0d1-fbcffb0e0dfd" />


## Result

The Morphological Opening and Closing operations were successfully implemented using Python and OpenCV.

The Opening operation removes small noise and smooths the object boundaries.
The Closing operation fills small holes and connects nearby regions in the image.

The original, opened, and closed images were displayed successfully using Matplotlib.
