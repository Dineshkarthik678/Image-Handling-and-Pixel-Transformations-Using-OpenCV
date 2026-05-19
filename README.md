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
- Name:DINESH KARTIK R
- Register Number:  212224230068

  ### Ex. No. 01

#### 1. Read the image ('DK.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('dk.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 2. Print the image width, height & Channel.
```python

image = cv2.imread('dk.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```

#### 3. Display the image using matplotlib imshow().
```python

plt.imshow(img_rgb, cmap='viridis') 
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
image = cv2.imread('dk.jpg') 
img = cv2.imread('dk.png',image)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img = cv2.imread('dk.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 7. Crop the image to extract any specific object from the image.
```python
crop = img_rgb[0:600,200:550] 
plt.imshow(crop[:,:,::-1])
plt.title("Cropped Region")
plt.axis("off")
plt.show()
crop.shape
```

#### 8. Resize the image up by a factor of 2x.
```python
image = cv2.imread('dk.jpg')
resized_image = cv2.resize(image, (1600// 2, 1200 // 2))
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

#### 9. Flip the cropped/resized image horizontally.
```python

image = cv2.imread('dk.jpg')
flipped_horizontally = cv2.flip(image, 1)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
img=cv2.imread('Apollo-11-launch.jpg',cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = cv2.putText(img_rgb, "Apollo 11 Saturn V Launch, July 16, 1969", (300, 700),cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)  
plt.imshow(text, cmap='gray')  
plt.title("New image")
plt.show()  

```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = (255,0,255)
cv2.rectangle(img_rgb, (400, 100), (800, 650), rect_color, 3)  
```

#### 13. Display the final annotated image.
```python
plt.title("Annotated image")
plt.imshow(img_rgb)
plt.show()
```

#### 14. Read the image ('Boy.jpg').
```python
img =cv2.imread('boy.jpg',cv2.IMREAD_COLOR)
img_rgb= cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 
```

#### 15. Adjust the brightness of the image.
```python
n = np.ones(img_rgb.shape, dtype="uint8") * 50
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
# YOUR CODE HERE
```

#### 18. Modify the image contrast.
```python
matrix1 = np.ones(img_rgb.shape, dtype="float32") * 1.1
matrix2 = np.ones(img_rgb.shape, dtype="float32") * 1.2
img_higher1 = cv2.multiply(img.astype("float32"), matrix1).clip(0,255).astype("uint8")
img_higher2 = cv2.multiply(img.astype("float32"), matrix2).clip(0,255).astype("uint8")
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```
plt.figure(figsize=(10,5))
plt.subplot(1,3,1), plt.imshow(img), plt.title("Original Image"), plt.axis("off")
plt.subplot(1,3,2), plt.imshow(img_higher1), plt.title("Higher Contrast (1.1x)"), plt.axis("off")
plt.subplot(1,3,3), plt.imshow(img_higher2), plt.title("Higher Contrast (1.2x)"), plt.axis("off")
plt.show()
```

#### 20. Split the image into the B,G,R components & Display the channels.
```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

#### 21. Merged the R, G, B , displays along with the original image
```python
image = cv2.imread('dk.jpg')
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
#### 23. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.cvtColor(img, cv2.COLOR_HSV2RGB)
combined = np.concatenate((img_rgb, merged_hsv), axis=1)
plt.figure(figsize=(10, 5))
plt.imshow(combined)
plt.title("Original Image  &  Merged HSV Image")
plt.axis("off")
plt.show()
```

## Output:
- **i)** Read and Display an Image.
<img width="800" height="702" alt="image" src="https://github.com/user-attachments/assets/52b65ddf-29ab-4a9b-bd82-593046cd8df9" />

<img width="400" height="640" alt="image" src="https://github.com/user-attachments/assets/66c48491-f415-4cf6-9418-4be0888248e9" />
<img width="574" height="643" alt="image" src="https://github.com/user-attachments/assets/89d0d90e-3f57-418b-add8-e4c16e2eef80" />
<img width="647" height="670" alt="image" src="https://github.com/user-attachments/assets/9d791eb6-9aa7-475e-9c1d-8411d8858cf2" />



<img width="591" height="686" alt="image" src="https://github.com/user-attachments/assets/7b1a9c3b-7135-4486-8ea3-189fde8bb054" />

<img width="750" height="684" alt="image" src="https://github.com/user-attachments/assets/b3fcb024-9767-4b96-b945-d5abf2a1411e" />

- **ii)** Adjust Image Brightness.

<img width="750" height="684" alt="image" src="https://github.com/user-attachments/assets/1e9e1001-d6cc-4f79-bb75-36ea826dd2c2" />


- **iii)** Modify Image Contrast.

<img width="802" height="753" alt="image" src="https://github.com/user-attachments/assets/5e12e1fa-c144-4525-8f9f-2b471d377f48" />

<img width="900" height="721" alt="image" src="https://github.com/user-attachments/assets/66ae684e-4503-4433-a85c-821cf13a053c" />

<img width="757" height="662" alt="image" src="https://github.com/user-attachments/assets/fcffa2a4-7512-4e65-aa01-0fe23983be07" />

- **iv)** Generate Third Image Using Bitwise Operations.

<img width="843" height="707" alt="image" src="https://github.com/user-attachments/assets/57e9d800-d3a6-4d91-897f-526e0b544536" />

<img width="678" height="695" alt="image" src="https://github.com/user-attachments/assets/1e6aabcd-9f71-4cd7-8e5c-3fd22d47fdc9" />

<img width="907" height="780" alt="image" src="https://github.com/user-attachments/assets/ce2ae961-6ead-4a9e-a6f0-7d04cfaa511b" />


<img width="766" height="652" alt="image" src="https://github.com/user-attachments/assets/35cb43bd-d5bf-4ab3-9b4d-65bc8b6f4256" />

<img width="929" height="730" alt="image" src="https://github.com/user-attachments/assets/caeaca60-eb2a-4563-8bb0-87f92e8edeb2" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
