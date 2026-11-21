# Implementation of Opening and Closing Using OpenCV

## Aim

To implement morphological **Opening** and **Closing** operations on an image using Python and OpenCV.

## Software Required

1. Anaconda – Python 3.7 (or higher)
2. OpenCV (`cv2`)
3. NumPy
4. Matplotlib

## Algorithm

### Step 1:
Import the necessary packages (`cv2`, `numpy`, and `matplotlib.pyplot`).

### Step 2:
Create a blank black image (`500 x 500`) using NumPy and insert white text onto it using `cv2.putText()`.

### Step 3:
Create a `3 x 3` square structuring element (kernel) using `np.ones()`.

### Step 4:
Apply the **Opening** operation (erosion followed by dilation) using `cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)` and display the result.

### Step 5:
Apply the **Closing** operation (dilation followed by erosion) using `cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)` and display the result.

## Program

```python
# Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)

# Create the Text using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'SANTHOSE AROCKIARAJ J', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)

# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')
plt.show()

# Create the structuring element (3x3 square kernel)
kernel = np.ones((3, 3), np.uint8)

# Use Opening operation (erosion followed by dilation)
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
plt.show()

# Use Closing Operation (dilation followed by erosion)
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# Display the result of Closing
plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Closing Operation")
plt.axis('off')
plt.show()
```

## Developed By

* **Name:** SURYA D
* **Register No:** 212224220115

## Output

### Display the Input Image
* A `500 x 500` black background image containing the white text `SANTHOSE AROCKIARAJ J` is displayed.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/e3866a28-5a79-4d78-94da-88686b124acf" />


### Display the Result of Opening
* The image after applying `cv2.MORPH_OPEN` is displayed. Opening performs erosion followed by dilation, which removes small external noise/thin strokes while preserving the overall shape and size of larger foreground characters.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/756e7870-8f83-4f2e-9d29-e5d8711c033f" />


### Display the Result of Closing
* The image after applying `cv2.MORPH_CLOSE` is displayed. Closing performs dilation followed by erosion, which closes small internal holes or gaps within the foreground characters.

<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/9793edd5-b046-4dc0-98bb-6abd2cc9ea25" />


## Result

Thus, the Opening and Closing operations are successfully implemented on the image using Python and OpenCV.
