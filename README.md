# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By:BHAVATHARANI S 
# Register Number: 212223230032
import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread('/content/abdul kalam.jpeg',cv2.IMREAD_GRAYSCALE)
plt.title("gray image")
plt.imshow(image,cmap='gray')
plt.axis('off')
plt.title("Histogram of Grayscale Image")
plt.hist(image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
equalized_gray_image = cv2.equalizeHist(image)
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
color_image = cv2.imread('/content/images (3).jpeg')
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
plt.title("Histogram Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')
blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])
equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])
```
## Output:
### Input Grayscale Image and Color Image
![image](https://github.com/user-attachments/assets/49948ac1-50ca-4d7f-9928-6429739fcbb0)


### Histogram of Grayscale Image and any channel of Color Image

![image](https://github.com/user-attachments/assets/6faea124-39ff-4413-ba63-7ed06840b2cb)


### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/26857ff2-6e6a-4ce1-a724-db36b465828e)



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
