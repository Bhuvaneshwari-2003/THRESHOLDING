# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import the necessary packages.

### Step2:
Create the Text using cv2.putText.

### Step3:
Create the Global thresholding to segment the image.

### Step4:
Create Adaptive thresholding to segment the image.

### Step5:
Otsu's method to segment the image.

### Step6:
End the program.

## Program
``
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("dog.png")
plt.imshow(image)
plt.title('original image')
plt.axis('off')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
plt.imshow(gray_img,'gray')
plt.title('Gray image')
plt.axis('off')

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray_img,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray_img,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray_img,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(gray_img,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(gray_img,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[gray_img,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
```
for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
    
```

## Output

### Original Image
![image](https://github.com/Bhuvaneshwari-2003/THRESHOLDING/assets/94828604/c5ddd007-e98f-4172-abe9-fd0e6ebe3ed9)


### Global Thresholding
![image](https://github.com/Bhuvaneshwari-2003/THRESHOLDING/assets/94828604/d569df30-245f-4285-b8a3-36cafb2eda2b)


### Adaptive Thresholding
![image](https://github.com/Bhuvaneshwari-2003/THRESHOLDING/assets/94828604/ec79acf1-66d0-4dd5-b51c-9ed774aeaf14)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Bhuvaneshwari-2003/THRESHOLDING/assets/94828604/c9ecef09-b67a-4eef-8d4e-3bc456e352b5)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

