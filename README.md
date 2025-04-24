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
![image](https://github.com/user-attachments/assets/c54908da-e9de-4848-82e1-827814df55fd)

![image](https://github.com/user-attachments/assets/60f2a230-4417-43b3-bcca-7246c47d4fd4)



### Histogram of Grayscale Image and any channel of Color Image
![image](https://github.com/user-attachments/assets/75106bbf-e80f-4c71-9f34-21401c0a33b2)

![image](https://github.com/user-attachments/assets/42ca3df6-a0ae-448b-9715-2b2e9d67e805)


### Histogram Equalization of Grayscale Image.
![image](https://github.com/user-attachments/assets/be8022bb-0528-489d-a025-6d560e109186)




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
