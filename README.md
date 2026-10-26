# EXP-1-DIPT
# EXP-1-Image Handling and Pixel Transformation Using Opencv
## NAME : RAGASUDHA R
## REG NO :212224230215
## DATE : 23/10/2026
# PROCEDURE:
Step1:

Load an image from your local directory and display it.
Step2:

o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.

Step3:

o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.

Step4:

o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.

Step5:

o Resize the original image to half its size and display it.

Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

Step7:
o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.

Step8:
o Save the final modified image to your local directory.

## CODE

```
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('photo.jpeg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
# Load the image
image = cv2.imread('photo.jpeg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 255, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,255),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 255, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "RAGASUDHA R", (100, 100), cv2.FONT_HERSHEY_SIMPLEX, 3, (0, 255, 0), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('photo.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('photo.jpeg')
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('photo.jpeg')
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[90:850, 90:850]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('photo.jpeg')
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
## OUTPUT
<img width="937" height="551" alt="image" src="https://github.com/user-attachments/assets/f780e81c-d47c-4d94-a3cc-22506ac119ef" />
<img width="1062" height="520" alt="image" src="https://github.com/user-attachments/assets/b991ba63-3b75-4371-bbdf-f9ab55fa4fe1" />
<img width="1106" height="517" alt="image" src="https://github.com/user-attachments/assets/4ff5cec1-280f-4f9a-be36-9587a2caf446" />
<img width="962" height="512" alt="image" src="https://github.com/user-attachments/assets/e96b1cb0-f2ac-4dd3-8db0-8ccb60dec0a5" />
<img width="860" height="511" alt="image" src="https://github.com/user-attachments/assets/9e1d9bc9-3d4e-498c-a91a-1f1b392ee6a9" />
<img width="1016" height="560" alt="image" src="https://github.com/user-attachments/assets/1850cba1-62fb-4dea-bae6-f2e68457eadd" />
<img width="887" height="557" alt="image" src="https://github.com/user-attachments/assets/c79bc692-1b40-4377-b3cd-e8ad275a7135" />
<img width="827" height="552" alt="image" src="https://github.com/user-attachments/assets/8867a7a5-9f63-42f6-8130-beefdb8634e9" />
<img width="996" height="555" alt="image" src="https://github.com/user-attachments/assets/bed9287a-b9c8-4ea4-b8ba-e840518e1676" />
<img width="847" height="562" alt="image" src="https://github.com/user-attachments/assets/873ef37c-55c1-40a6-94bd-8a3c69f8159d" />
<img width="762" height="512" alt="image" src="https://github.com/user-attachments/assets/f2223982-29e2-4f0c-af44-1bc15327e64f" />
<img width="872" height="525" alt="image" src="https://github.com/user-attachments/assets/e3b40af9-af7c-475c-a672-01162fef06a6" />
<img width="870" height="512" alt="image" src="https://github.com/user-attachments/assets/9f4a7808-aa07-482a-bcf5-ce4e7e385add" />
<img width="972" height="550" alt="image" src="https://github.com/user-attachments/assets/f5624b34-cfae-471d-9b9d-cd5052499371" />
<img width="930" height="550" alt="image" src="https://github.com/user-attachments/assets/b4d54bdf-55fa-4e26-ac1e-6ce551b122ca" />

## RESULT
Thus the Image Handling and Pixel Transformation Using Opencv was verified successfully.
