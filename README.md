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
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/2025b34a-c94b-4637-834a-be5497d6665d" width=65%>

<br>

### Global Thresholding
<br>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/e71e6231-1988-4cfe-9895-7f3af798859f" width=65%>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/a7d02d51-79a2-4dfc-9c8f-4ddf1be9ef2b" width=65%>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/9152ae90-691f-42c4-a972-9d42ad8efc5b" width=65%>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/7960572e-11ce-4b99-8216-516a576cef35" width=65%>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/0cb1621b-1ed3-43f9-aa90-d8730ce6a598" width=65%>

<br>

### Adaptive Thresholding
<br>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/9adda608-b381-48aa-a18d-ff17cf5fc194" width=65%>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/d3b46286-b5dd-4e0b-8d86-f18737aa7964" width=65%>

<br>


### Optimum Global Thesholding using Otsu's Method
<br>
<img src="https://github.com/Jenishajustin/Thresholdingg/assets/119405070/ea95e603-397a-4666-a19b-f0822f656124" width=65%>

<br>

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
