# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
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
- **Name:** JANANI SARASWATHI S  
- **Register Number:** 212225230110

### Ex. No. 01
Step1: Load an image from your local directory and display it.
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('dog.jpg',cv2.IMREAD_COLOR)
img_rgb= cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')
plt.title("ORIGINAL IMAGE")
plt.axis('off')
print("DEVELOPED BY:JANANI SARASWATHI S")
print("REGISTER NUMBER : 212225230110")
plt.show()
```
Step2: o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image.

o Draw a rectangle around a specific region of interest in the image.

o Add the text "OpenCV Drawing" at the top-left corner of the image. Load the image
```
image = cv2.imread('dog.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
img_rgb.shape
```
Draw a line from top-left to bottom-right.
```
line_img = cv2.line(img_rgb, (337, 0), (0, 600), (255, 0, 0), 3)
line_img2 = cv2.line(line_img, (0, 0), (337, 600), (255, 0, 0), 3)
plt.imshow(line_img2)  
plt.title("Image with Line")
plt.axis('on')  
plt.show()
```
Draw a square at the center of the image. Load the image
```
img = cv2.imread('dog.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img = cv2.imread('dog.jpg')
img_rgb= cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
square_img = cv2.rectangle(img_rgb, (85, 185), (255, 355), (255, 0, 0), 4)
plt.imshow(square_img)
plt.title("IMAGE WITH SQUARE")
plt.axis("off")
plt.show()
```
Draw a rectangle around the whole image Load the image
```
img = cv2.imread('dog.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb= cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img.shape
```
Draw a rectangle around the Whole image
```
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (335, 600), (255, 0, 0), 7)
plt.imshow(rectangle_img,cmap='viridis')
plt.title("IMAGE WITH RECTANGLE")
plt.axis("off")
plt.show()
```
Add the text "OpenCV Drawing" at the top-left corner of the image. Load the image
```
img = cv2.imread('dog.jpg')
```
Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
img_rgb=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
```
Add text to the image
```
text_img = cv2.putText(img_rgb,"PUPPY",(1,50),cv2.FONT_HERSHEY_SIMPLEX,2,(255,255,255),3)
plt.imshow(text_img,cmap="viridis")
plt.axis('off')
plt.title("IMAGE WITH TEXT")
plt.show() 
```
Step3: o Convert the image from RGB to HSV and display it.

o Convert the image from RGB to GRAY and display it.

o Convert the image from RGB to YCrCb and display it.

o Convert the HSV image back to RGB and display it.
Load the image
```
img = cv2.imread('dog.jpg')
img_rgb= cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb)
plt.title("ORIGINAL RGB IMAGE")
plt.axis('off')
plt.show()
```
Convert RGB to HSV
```
img_hsv=cv2.cvtColor(img_rgb,cv2.COLOR_RGB2HSV)
```
HSV Image
```
plt.imshow(img_hsv)
plt.title("HSV IMAGE")
plt.axis("off")
plt.show()
```
Convert RGB to GRAY
```
img_gray=cv2.cvtColor(img_rgb,cv2.COLOR_RGB2GRAY)
```
Grayscale image
```
plt.imshow(img_gray,cmap='gray')
plt.title("GRAYSCALE IMAGE")
plt.axis("off")
plt.show()
```
Convert RGB to YCrCb
```
img_hsv_to_rgb=cv2.cvtColor(img_hsv,cv2.COLOR_HSV2RGB)
```
YCrCb Image
```
img_gray=cv2.cvtColor(img_rgb,cv2.COLOR_RGB2YCrCb)
plt.imshow(img_gray)
plt.title("YCrCb IMAGE")
plt.axis("off")
plt.show()
```
Convert HSV back to RGB4
```
img_hsv_to_rgb=cv2.cvtColor(img_hsv,cv2.COLOR_HSV2RGB)
plt.imshow(img_hsv_to_rgb)
plt.title("HSV TO RGB IMAGE")
plt.axis('off')
plt.show()
```
Step4: o Access and print the value of the pixel at coordinates (100, 100).

o Modify the color of the pixel at (200, 200) to white.

Modify a block of pixels (300x300) to white, starting from (200, 200)
```
img_rgb[225:425, 120:320] = [255,255, 255]
```
Convert BGR to RGB for displaying with Matplotlib
```
img2_rgb = cv2.cvtColor(img2,cv2.COLOR_BGR2RGB)
```
Display the modified image
```
plt.imshow(image_rgb)
plt.title("Image with 200x200 White Block")
plt.axis("off")
plt.show()
img2 = cv2.imread('passport.jpeg')
img = cv2.imread('dog.jpg')
img_rgb = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
```
Resize while keeping aspect ratio
```
resize_img = cv2.resize(img,(338//2,601//2))
img_rgb=cv2.cvtColor(resize_img,cv2.COLOR_BGR2RGB)
img_rgb.shape
plt.imshow(img_rgb,cmap='viridis')
plt.title('IMAGE WITHIN A IMAGE ')
plt.axis('off')
plt.show()
```
Step5: o Resize the original image to half its size and display it. Load the image
```
img = cv2.imread('dog.jpg')
img.shape
```
Convert BGR to RGB for displaying with Matplotlib
```
resize_img = cv2.resize(img,(1379//2,736//2))
img_rgb.shape
```
Display the resized image
```
plt.imshow(img_rgb,cmap='viridis')
plt.axis('off')
plt.title("RESIZED IMAGE (HALF SIZE)")
plt.show()
```
Step6: o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
```
img = cv2.imread('dog.jpg')
```
Crop a 200x200 region starting from (50, 50)
```
roi = img[80:550,10:328]
```
Convert BGR to RGB for displaying with Matplotlib
```
roi_rgb = cv2.cvtColor(roi,cv2.COLOR_BGR2RGB)
```
Display the cropped region (ROI)
```
plt.imshow(roi_rgb)
plt.axis('off')
plt.title("CROPPED REGION OF INTEREST (ROI)")
plt.show()
```
Step7: o Flip the original image horizontally and display it.

o Flip the original image vertically and display it.

Load the image
```
img = cv2.imread('dog.jpg')
flip_hor = cv2.flip(image,1)
flip_hor_rgb = cv2.cvtColor(flip_hor,cv2.COLOR_BGR2RGB)
```
Horizontal flip
```
plt.imshow(flip_hor_rgb)
plt.axis('off')
plt.title("FLIPPED HORIZONTALLY")
plt.show()
```
Flip the image vertically (up-down)
```
flip_vert = cv2.flip(img,0)
```
Convert BGR to RGB for displaying with Matplotlib
```
flip_vert_rgb = cv2.cvtColor(flip_vert,cv2.COLOR_BGR2RGB)
plt.imshow(flip_vert_rgb)
plt.axis('off')
plt.title("FLIPPED VETICALLY")
plt.show()
```
Step8: o Save the final modified image to your local directory.
OUTPUT:

<img width="372" height="566" alt="image" src="https://github.com/user-attachments/assets/b826728c-cbc8-48eb-9bb4-d06f70c54933" />

<img width="392" height="555" alt="image" src="https://github.com/user-attachments/assets/fc3e19fc-5053-4188-9aba-0d046dcb8fa1" />

<img width="386" height="517" alt="image" src="https://github.com/user-attachments/assets/bdf04499-b758-4c13-bd53-c8331ccac8d7" />

<img width="341" height="502" alt="image" src="https://github.com/user-attachments/assets/fe782c24-0f59-4649-a9b9-013f7a551147" />

<img width="350" height="521" alt="image" src="https://github.com/user-attachments/assets/cea8c2cb-40cd-4ed4-b696-95e0ff44df33" />

<img width="305" height="517" alt="image" src="https://github.com/user-attachments/assets/4778d859-9e40-4a8c-a451-60c3db81aa8d" />


<img width="316" height="507" alt="image" src="https://github.com/user-attachments/assets/8a602703-dea5-42fd-86ff-cdf2f3ba9dd5" />


<img width="307" height="527" alt="image" src="https://github.com/user-attachments/assets/b9de732e-85d3-4f2d-aaa6-d610a1566b76" />


<img width="320" height="520" alt="image" src="https://github.com/user-attachments/assets/418a7e01-8a4f-4942-bfa9-6121158504ac" />

<img width="313" height="542" alt="image" src="https://github.com/user-attachments/assets/306a534a-bb65-4313-834d-8e8466a66a3e" />

<img width="416" height="510" alt="image" src="https://github.com/user-attachments/assets/b934e4d0-c033-4d20-8014-e1a6258a06d8" />

<img width="353" height="537" alt="image" src="https://github.com/user-attachments/assets/0ac376ab-5e9c-4b80-9240-f06e54fd79a9" />

<img width="432" height="512" alt="image" src="https://github.com/user-attachments/assets/66a11eaf-5bcd-43e6-838e-2a8c8beeb5d9" />

<img width="297" height="507" alt="image" src="https://github.com/user-attachments/assets/1f5fe1e6-8a67-45c0-bbf9-09d09af37f2b" />

<img width="290" height="507" alt="image" src="https://github.com/user-attachments/assets/0e9c02fe-7800-4c86-b77d-93951e0ca81b" />



## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

