# EXP-8 THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

- **Step1:** Load the necessary packages.

- **Step2:** Read the Image and convert to grayscale.

- **Step3:** Use Global thresholding to segment the image.

- **Step4:** Use Adaptive thresholding to segment the image.

- **Step5:** Use Otsu's method to segment the image and display the results.

## Program
### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```


### Read the Image and convert to grayscale
```python
image = cv2.imread('mountain.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('mountain.jpg',0)
```

### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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



## Output

### Original Image
<br>

![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/275c7d91-68ac-422c-93a3-7a787ad762ea)

<br>

### Global Thresholding
<br>

![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/f56feda0-64d4-4bd8-8b35-74b54a771738)
![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/16367ce1-6fac-44c2-8fbd-d7179f326bf3)
![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/29bf6154-93ba-4723-b370-4f1017e5eafc)
![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/efe4ea74-7b2a-443e-97ff-75b9e55f5d6f)
![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/f5c69731-0fed-4435-b591-614282824ea8)

<br>

### Adaptive Thresholding
<br>

![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/82b51f44-3616-4c9e-8ed9-58d1dd08840c)
![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/ff0e7448-6a71-4088-bd86-10463ac3d61a)

<br>


### Optimum Global Thesholding using Otsu's Method
<br>

![image](https://github.com/RagulRM/Thresholdingg/assets/121609342/62ffd49a-7d67-47c9-8f21-3338e1c7746c)

<br>

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
