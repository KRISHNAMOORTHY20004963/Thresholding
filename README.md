# Thresholding
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("sun.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("sun.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_sun1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_sun2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_sun3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_sun4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_sun5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Otsu's method to segment the image 
ret,thresh_sun6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Adaptive thresholding to segment the image
thresh_sun7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_sun8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_sun1,thresh_sun2,thresh_sun3,thresh_sun4,thresh_sun5,thresh_sun6,thresh_sun7,thresh_sun8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
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
## OUTPUT:

### Original Image and Grayscale Image
![image][huh 1](https://user-images.githubusercontent.com/75241177/171125878-21972f45-79ba-42d7-9f6e-3c8728654b77.jpg)


### Global Thresholding
![image]![huh 2](https://user-images.githubusercontent.com/75241177/171125911-3a06f0ce-79bb-4d3e-9b01-2be59bb87ce7.jpg)

![image]![huh 3](https://user-images.githubusercontent.com/75241177/171126007-e06b4511-c010-46b4-a6c1-d9bd4d862f55.jpg)



![image]![huh 4](https://user-images.githubusercontent.com/75241177/171126114-23e47d5b-cf48-4c39-bb6f-02d96da18cff.jpg)



![image]![huh 5](https://user-images.githubusercontent.com/75241177/171126300-098be4be-6883-4c4f-94f5-4deec428a49d.jpg)

![image]![huh 6](https://user-images.githubusercontent.com/75241177/171126323-176543e0-0229-472e-9c1f-ebbb608783ec.jpg)

### Adaptive Thresholding

![image]![huh 7](https://user-images.githubusercontent.com/75241177/171126453-afad2b77-a00e-4ae9-ab04-4090fa2f4b81.jpg)



![image]![huh 8](https://user-images.githubusercontent.com/75241177/171126525-b6c9642f-4c6c-478c-b2e9-442e362e0e58.jpg)


### Optimum Global Thesholding using Otsu's Method
![image]![huh 9](https://user-images.githubusercontent.com/75241177/171126590-a31cb001-6ef5-439c-9988-b7ffdf282090.jpg)


## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

