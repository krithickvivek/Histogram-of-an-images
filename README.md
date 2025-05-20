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
### Developed By: Krithick Vivekananda
### Register Number: 212223240075
```python
import matplotlib.pyplot as plt 
import cv2

grayscale_image = cv2.imread("Spidys.jpg", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("Spidys.jpg")

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
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
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
![image](https://github.com/user-attachments/assets/2a2bdcf1-c5cc-4828-86e9-110b01cc8672)

![image](https://github.com/user-attachments/assets/480ffd9a-0cee-4292-a145-a7b91af7619e)

### Histogram of Grayscale Image and any channel of Color Image
![image](https://github.com/user-attachments/assets/9593e476-26e6-4397-b535-3ea783a0a1f3)
![image](https://github.com/user-attachments/assets/3b954134-ffad-482f-9c70-633b511995a7)

### Histogram Equalization of Grayscale Image.
![image](https://github.com/user-attachments/assets/39f68ee5-48cf-49ba-ac4c-36ac6910df09)


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
