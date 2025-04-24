![image](https://github.com/user-attachments/assets/77212c97-47f1-498b-adbc-7622aab69dbf)# Histogram-of-an-images
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
# Developed By: Bhavatharani S
# Register Number: 212223230032
import matplotlib.pyplot as plt 
import cv2

grayscale_image = cv2.imread("snoopy.jpg", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("snoopy.jpg")

gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(grayscale_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(colourscale_image, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')

plt.show()

plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.plot(gray_hist, color='black')
plt.title("Grayscale Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")

plt.subplot(1, 2, 2)
plt.plot(hist_r, color='red')
plt.plot(hist_b, color='blue')
plt.plot(hist_g, color='green')
plt.title("Color Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")

plt.show()

equalized_grey_img = cv2.equalizeHist(grayscale_image)
plt.title("Equalized Hist of Gray Image")
plt.hist(equalized_grey_img.ravel(),bins=256,color='black',alpha=0.6)
plt.show()
```
## Output:
### Input Grayscale Image and Color Image
![image](https://github.com/user-attachments/assets/8eade1a3-1b33-47b0-8cc5-3dbc9144885d)

![image](https://github.com/user-attachments/assets/2c72fc67-97ec-42a8-8632-412be1778880)



### Histogram of Grayscale Image and any channel of Color Image

![image](https://github.com/user-attachments/assets/eb805a64-e07c-465d-951c-2ecc57b2e57a)

![image](https://github.com/user-attachments/assets/2d34bc57-b5a9-4cd9-ab03-f48f7542b351)


### Histogram Equalization of Grayscale Image.
![image](https://github.com/user-attachments/assets/7d8edb62-71e6-47bc-957a-09bc6efe17fc)



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
