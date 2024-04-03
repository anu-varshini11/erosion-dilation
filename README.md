# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import necessary packages

### Step2:
Create an empty window and add text to it
### Step3:
create a structuring element

### Step4:
Do the operation

### Step5:
Show the output image


 
## Program:

``` Python
import cv2
import numpy as np
from matplotlib import pyplot as plt

#to read the color image
input_image_path='picture.jpg'
color_image=cv2.imread(input_image_path)

#convert the color image to grayscale
gray_image=cv2.cvtColor(color_image,cv2.COLOR_BGR2GRAY)

#perform edge detection using Canny
edges=cv2.Canny(gray_image,100,200)

#define the kernel size for erosion and dilation
kernel_size=5
kernel=np.ones((kernel_size,kernel_size),np.uint8)

#perform erosion
erosion=cv2.erode(edges,kernel,iterations=1)

#perform dilation
dilation=cv2.dilate(edges,kernel,iterations=1)

#display all images
plt.figure(figsize=(15,10))

plt.subplot(2,3,1)
plt.imshow(cv2.cvtColor(color_image,cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2,3,2)
plt.imshow(gray_image,cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2,3,3)
plt.imshow(edges,cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2,3,4)
plt.imshow(erosion,cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2,3,5)
plt.imshow(dilation,cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()
```
## Output:

### Display the input Image
![Screenshot 2024-04-03 101257](https://github.com/anu-varshini11/erosion-dilation/assets/138969827/06efc3a7-9968-4a43-a69b-8a7bde22f331)

### Display the Eroded Image
![Screenshot 2024-04-03 101314](https://github.com/anu-varshini11/erosion-dilation/assets/138969827/bb372a9b-1405-4f48-828d-ed0d4936de05)

### Display the Dilated Image
![Screenshot 2024-04-03 101332](https://github.com/anu-varshini11/erosion-dilation/assets/138969827/a463c8be-898c-4299-bf8a-2f8cffd69aaf)

### Full output
![Screenshot 2024-04-03 101348](https://github.com/anu-varshini11/erosion-dilation/assets/138969827/08134e02-6ba5-4c33-ac83-df410c805b22)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
