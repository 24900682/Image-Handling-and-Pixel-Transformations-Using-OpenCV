## Ex. No. 01 - Image-Handling-and-Pixel-Transformations-Using-OpenCV 
## Name : ASWIN L
## Reg No : 212224230028
## Date : 22/09/25


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
Split the image (boy.jpg) into B, G, R components and display the channel

## PROGRAM DEVELOPED BY:
~~~
NAME : ASWIN L
REG NO: 212224230028
~~~


#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('me.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 2. Display the image using matplotlib imshow().
```
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 4. # Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
```
image = cv2.imread('me.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```

#### 5. Draw a line from top-left to bottom-right
```
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
```

#### 6. Display the image with Circle
```
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
```

#### 7. Display the image with Rectangle
```
image = cv2.imread('me.jpg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 8. Add text to the image
```
image = cv2.imread('me.jpg') 
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
text_img = cv2.putText(img_rgb, "Good Morning", (40, 80), cv2.FONT_HERSHEY_SIMPL
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```

#### 9. Original RGB Image
```
image = cv2.imread('me.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

#### 10. Convert RGB to HSV
```
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
```

#### 11. HSV Image
```
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

```

#### 12. Convert RGB to GRAY
```
 image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
```

#### 13. Grayscale Image
```
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 14. Convert RGB to YCrCb
```
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
```

#### 15. YCrCb Image
```
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```

#### Convert HSV back to RGB
```
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off") 
```

#### 17.  Display the modified image
```
image[100:300, 200:300] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
```

#### 18. Resize the image to half its size
```
image = cv2.imread('me.jpg')
image.shape
resized_image = cv2.resize(image, (768 // 2, 600 // 2))

```

#### 19. Display the resized image
```
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

#### 20. Crop a 300x300 region starting from (50, 50)
```
image = cv2.imread('me.jpg')
image.shape
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
```

#### 21. Display the cropped region (ROI)
```
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

#### 22. Flip the image horizontally (left-right)
```
image = cv2.imread('me.jpg')
flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```
#### 23. Flip the image vertically (up-down)
```
flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

## Output:
**i)** Read and Display an Image.
1.Read 'me.jpg' as grayscale and display:


<img width="413" height="562" alt="Screenshot 2025-09-22 112328" src="https://github.com/user-attachments/assets/9c827791-1938-4f96-92ea-e1e908ee4113" />







 2.Image with Line:



<img width="431" height="558" alt="Screenshot 2025-09-22 112337" src="https://github.com/user-attachments/assets/38d948a2-fc31-45df-b241-371ad49a20e4" />

 





  
  3.Image with circle




<img width="445" height="551" alt="Screenshot 2025-09-22 112343" src="https://github.com/user-attachments/assets/1af6f51f-2e7f-446d-a5f8-7afa1e33fcaf" />

  
  





  
  4. Image with Rectangle:




<img width="449" height="559" alt="Screenshot 2025-09-22 112353" src="https://github.com/user-attachments/assets/94a7e88b-7b8d-480e-ab38-d5490fb83762" />







  
  5. Image with Text:


<img width="404" height="549" alt="Screenshot 2025-09-22 112400" src="https://github.com/user-attachments/assets/952affd6-6134-4496-b40c-607b7237778c" />








6. Orginal RGB Image:



<img width="402" height="561" alt="Screenshot 2025-09-22 112408" src="https://github.com/user-attachments/assets/4e5434f7-ca19-4b6a-82b4-90e2290a755f" />





7. HSV Image


<img width="447" height="578" alt="Screenshot 2025-09-22 112422" src="https://github.com/user-attachments/assets/037553d6-eae6-44dc-a03f-2091c08c6571" />






8. Grayscale Image



<img width="418" height="572" alt="Screenshot 2025-09-22 112428" src="https://github.com/user-attachments/assets/447ea295-21d9-47bc-9f01-2742d068da8c" />







9. YCrCb Image


<img width="443" height="567" alt="Screenshot 2025-09-22 112434" src="https://github.com/user-attachments/assets/ccfc9e4f-c450-44f4-b070-6fb37e20f696" />

10. HSV to RGB Image:


<img width="411" height="565" alt="Screenshot 2025-09-22 112441" src="https://github.com/user-attachments/assets/cc58fea5-6a55-48b7-bb75-ad8644b9fe14" />


11. Image with 300x300 White Block:


<img width="428" height="559" alt="Screenshot 2025-09-22 112447" src="https://github.com/user-attachments/assets/ec5d4249-bc4a-4122-9309-c72dd5222983" />



12. Resized Image(Half Size):

<img width="666" height="583" alt="Screenshot 2025-09-22 112454" src="https://github.com/user-attachments/assets/f304deac-2612-415c-81d8-f26363548604" />


14. Cropped REGION Interest (ROI):


<img width="551" height="579" alt="Screenshot 2025-09-22 112500" src="https://github.com/user-attachments/assets/0c0304b8-5c73-422b-9c76-250b4ea7f379" />


15. Flipped Horizontally:

<img width="409" height="557" alt="Screenshot 2025-09-22 112505" src="https://github.com/user-attachments/assets/2bda75f8-cfd0-4bab-9cc0-af0e3efd3bc7" />

16. Flipped Vertically:

    <img width="429" height="572" alt="Screenshot 2025-09-22 112512" src="https://github.com/user-attachments/assets/0951228c-1334-477a-89eb-469f8fa7eb8d" />



## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
