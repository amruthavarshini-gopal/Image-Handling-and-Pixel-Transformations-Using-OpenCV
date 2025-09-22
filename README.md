# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## Aim:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** Amruthavarshini Gopal 
- **Register Number:** 212223230013

  ### Ex. No. 01

#### 1.Read the image using OpenCV
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
img =cv2.imread('photo1.jpeg',cv2.IMREAD_COLOR)
```

#### 2. Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```python
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 3. Display the image using matplotlib imshow().
```python
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```

#### 4. Draw a line from top-left to bottom-right
```python
img_rgb.shape
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

#### 5. Draw a circle in the image
```python
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

#### 6. Draw a rectangle around the Whole image
```python
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 7.  Add text to the image
```python
text_img = cv2.putText(img_rgb, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 0), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

#### 8. Original RGB Image
```python
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

#### 9. Convert RGB to HSV
```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```

#### 10. Convert RGB to GRAY
```python
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 11. Convert RGB to YCrCb
```python
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

#### 12. Convert HSV back to RGB
```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

#### 13. Modify a block of pixels (300x300) to white, starting from (200, 200)
```python
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
```

#### 14. Convert BGR to RGB for displaying with Matplotlib
```python
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
```

#### 15.Resize the image to half its size
```python
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
```

#### 16.Convert BGR to RGB for displaying with Matplotlib
```python
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
```

#### 17. Display the resized image
```python
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

#### 18. Crop a 300x300 region starting from (50, 50)
```python
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
```

#### 19. Display the cropped region (ROI)
```python
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

#### 20. Flip the image horizontally (left-right)
```python
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
```

#### 21. Horizontal flip
```python
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

#### 22. Flip the image vertically (up-down)
```python
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
```
#### 23. Vertical flip
```python
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

## Output:
- **i)** Read and Display an Image.
- <img width="508" height="413" alt="image" src="https://github.com/user-attachments/assets/d00a5d4b-dcb0-456f-bc93-75b507f9f5d2" />
<img width="552" height="417" alt="image" src="https://github.com/user-attachments/assets/d3e113b6-f874-4e86-8363-e6f2f6cfb90d" />
<img width="303" height="398" alt="image" src="https://github.com/user-attachments/assets/ccd7df0a-08b9-4763-bb48-6d50a45593aa" />
<img width="430" height="402" alt="image" src="https://github.com/user-attachments/assets/62a42a2c-8467-4654-b4ba-2fcbd880feea" />
<img width="561" height="338" alt="image" src="https://github.com/user-attachments/assets/80ed3956-f67f-4b53-89be-04dbc5786702" />

- **ii)** Adjust Image Brightness.
- <img width="964" height="340" alt="image" src="https://github.com/user-attachments/assets/2da0d8b2-688a-467a-96d7-b0677e7ff2ef" />

- **iii)** Modify Image Contrast.
- <img width="939" height="354" alt="image" src="https://github.com/user-attachments/assets/94f93d4d-3b67-4cf2-92e2-0853df57ee6a" />

- **iv)** Generate Third Image Using Bitwise Operations.
- <img width="1008" height="347" alt="image" src="https://github.com/user-attachments/assets/dca191d9-abeb-4b89-920e-fec0dc593df3" />
<img width="587" height="340" alt="image" src="https://github.com/user-attachments/assets/7effa124-4533-41c7-9fa2-b4704e1eed35" />
<img width="1068" height="383" alt="image" src="https://github.com/user-attachments/assets/8882058d-90d1-4c87-aed9-498f67e49bcc" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
