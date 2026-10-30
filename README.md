# Experiment 1: Image Handling and Pixel Transformations Using OpenCV

## Name: Pragatheeshraaj D
## Register Number: 212224230199


---

## AIM

To perform image handling and pixel transformations using Python and OpenCV, including reading and displaying images, drawing shapes, adding text, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving the modified image.

## SOFTWARE REQUIRED

- Python
- OpenCV
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

## INSTALLATION

Install the required libraries using the following command:

```bash
pip install opencv-contrib-python-headless matplotlib
```

## ALGORITHM

### Step 1: Read and Display an Image

1. Import OpenCV and Matplotlib libraries.
2. Read an image from the local directory using `cv2.imread()`.
3. Convert the image from BGR to RGB.
4. Display the original image using Matplotlib.

### Step 2: Draw Shapes and Add Text

1. Draw a line from the top-left to the bottom-right of the image.
2. Draw a circle at the center of the image.
3. Draw a rectangle around the image.
4. Add the text "OpenCV Drawing" at the top-left corner.

### Step 3: Color Space Conversion

1. Convert the RGB image to HSV and display it.
2. Convert the RGB image to grayscale and display it.
3. Convert the RGB image to YCrCb and display it.
4. Convert the HSV image back to RGB and display it.

### Step 4: Pixel Manipulation

1. Access and print the pixel value at coordinates `(100, 100)`.
2. Change the pixel at coordinates `(200, 200)` to white.
3. Modify a 300 × 300 region of the image to white.
4. Display the modified image.

### Step 5: Image Resizing

1. Read the original image.
2. Resize the image to half its original width and height.
3. Display the resized image.

### Step 6: Image Cropping

1. Read the original image.
2. Extract a 300 × 300 region of interest starting at `(50, 50)`.
3. Display the cropped image.

### Step 7: Image Flipping

1. Flip the original image horizontally.
2. Flip the original image vertically.
3. Display both flipped images.

### Step 8: Save the Final Modified Image

1. Save the modified image in the local directory using `cv2.imwrite()`.
2. Verify that the image has been saved successfully.

---

## PROGRAM

### Step 1: Read and Display an Image

```python
import cv2
import matplotlib.pyplot as plt

# Read the image
img = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg', cv2.IMREAD_COLOR)

# Convert BGR to RGB
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display the image
plt.imshow(img_rgb, cmap='viridis')
plt.title("Original Image")
plt.axis('off')
plt.show()
```

### Step 2: Draw Shapes and Add Text

#### 2.1 Draw a Line

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
img_rgb.shape

# Draw a line
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2)

# Display the image
plt.imshow(line_img, cmap='viridis')
plt.title("Image with Line")
plt.axis('off')
plt.show()
```

#### 2.2 Draw a Circle

```python
# Load the image
image = cv2.imread('Qno. 1.jpg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
img_rgb.shape

# Draw a circle
circle_img = cv2.circle(img_rgb, (400, 300), 150, (255, 0, 0), 10)

# Display the image
plt.imshow(circle_img, cmap='viridis')
plt.title("Image with Circle")
plt.axis('off')
plt.show()
```

#### 2.3 Draw a Rectangle

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
image.shape

# Draw a rectangle
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)

# Display the image
plt.imshow(rectangle_img, cmap='viridis')
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()
```

#### 2.4 Add Text to the Image

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Convert BGR to RGB
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "Pragatheeshraaj D", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 10)

# Display the image
plt.imshow(text_img, cmap='viridis')
plt.title("212224230199")
plt.axis('off')
plt.show()
```

### Step 3: Color Space Conversion

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the original RGB image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# Display HSV image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Display grayscale image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# Display YCrCb image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

# Display converted RGB image
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()
```

### Step 4: Pixel Manipulation

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Modify a block of pixels (300x300) to white
image[200:500, 200:500] = [255, 255, 255]

# Convert BGR to RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

### Step 5: Image Resizing

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Check image dimensions
image.shape

# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))

# Convert BGR to RGB
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

# Check resized image dimensions
resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

### Step 6: Image Cropping

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Check image dimensions
image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]

# Convert BGR to RGB
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

# Display the cropped region
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

### Step 7: Image Flipping

```python
# Load the image
image = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg')

# Flip the image horizontally
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

# Display horizontally flipped image
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()

# Flip the image vertically
flipped_vertically = cv2.flip(image, 0)

# Convert BGR to RGB
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Display vertically flipped image
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```

---

## OUTPUT

#The following outputs are obtained:

#1. Original image displayed using OpenCV and Matplotlib.


<img width="370" height="432" alt="image" src="https://github.com/user-attachments/assets/e574849c-b85d-4b98-987d-3c752e26c4ed" />




#2. Image with a line drawn from the top-left to the bottom-right.


<img width="353" height="420" alt="image" src="https://github.com/user-attachments/assets/d1f3d839-4afd-41b0-a4a1-864aedc055a5" />


#3. Image with a circle .


<img width="397" height="433" alt="image" src="https://github.com/user-attachments/assets/ebb557ba-9fa5-4529-a4c1-2226c41bad1f" />


#4. Image with a rectangle around its boundary.


<img width="327" height="392" alt="image" src="https://github.com/user-attachments/assets/bf73f707-521d-4add-a34c-faf10d83355b" />


#5. Image with the text "OpenCV Drawing".


<img width="331" height="406" alt="image" src="https://github.com/user-attachments/assets/8ce4b9ce-3b2d-451f-b0fb-9d0e2fc85bb1" />


#6. HSV, grayscale, and YCrCb color space conversions.

#HSV conversion

<img width="333" height="398" alt="image" src="https://github.com/user-attachments/assets/9bc6c05a-fee7-4a2b-921c-79b504fd5f49" />

#grayscale conversion

<img width="352" height="410" alt="image" src="https://github.com/user-attachments/assets/73b02f19-18f3-4591-a4ed-b42035021625" />

#YCrCb conversion

<img width="296" height="385" alt="image" src="https://github.com/user-attachments/assets/fcecc561-755d-4858-b733-047b89855740" />


#7. Image converted from HSV back to RGB.


<img width="328" height="405" alt="image" src="https://github.com/user-attachments/assets/d43f9b3a-c70b-45fa-ae6a-c4d5680a3ff2" />


#8. Pixel value displayed and a white region added to the image.


<img width="316" height="397" alt="image" src="https://github.com/user-attachments/assets/abfc9d56-6b37-4cdf-82f2-ff500bcc3bd7" />


#9. Image resized to half its original dimensions.


<img width="547" height="425" alt="image" src="https://github.com/user-attachments/assets/1aff623d-3bda-4163-8e6d-1d92b5833550" />


#10. Cropped region of interest displayed.


<img width="417" height="415" alt="image" src="https://github.com/user-attachments/assets/db68b6ae-d3ac-4882-b718-0ddcbe466a27" />


#11. Horizontally flipped image displayed.


<img width="340" height="410" alt="image" src="https://github.com/user-attachments/assets/96f0b4d2-a8f0-44ee-9eaa-5acf1c22d590" />


#12. Vertically flipped image displayed.


<img width="307" height="412" alt="image" src="https://github.com/user-attachments/assets/9abae030-79c8-43ef-a917-d5ea6aadf381" />



## RESULT

Thus, image handling and pixel transformations were performed using Python, OpenCV, and Matplotlib. The experiment demonstrated image reading, shape drawing, text insertion, color space conversion, pixel manipulation, image resizing, cropping, flipping, and saving.

---
