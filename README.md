# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: SATHISH R
### Register Number: 212222230138

### i) Read and display the image
```python
import cv2
image=cv2.imread('lion.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Lion-Sathish',image)
 cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 023301](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/98c12b12-6246-4bd8-9f11-2806136317cc)

### ii)Write the image
```python
import cv2
image=cv2.imread('lion.jpg',0)
cv2.imwrite('test.jpg',image)
```

#### Output:
![Screenshot 2024-02-15 024215](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/e5be0d15-0dd8-4c98-9cc3-033b6d35bec3)

### iii)Shape of the Image
```python
    import cv2
    image=cv2.imread('lion.jpg',1)
    print(image.shape)
```
#### Output:
![Screenshot 2024-02-15 024341](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/06dbea85-2946-4ebc-a7eb-5e30b72a62c1)

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('lion.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
        random.randint(0,255),
        random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

#### Output:
![Screenshot 2024-02-15 025133](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/8184e278-dd14-4884-874f-4d0f86605b7f)


### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('lion.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 025622](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/f04b7a92-192f-4795-aa3a-d6110fb9fa1a)


### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('lion.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 025942](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/4380aa71-17e6-4940-8dc1-c669745f867a)


### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('lion.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 030233](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/3b8c7987-5971-40b8-9a97-957b186acdf1)


### viii) RGB and BGR to YCrCb

```python
import cv2
img = cv2.imread('lion.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 030450](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/7f91ff01-72e4-40d5-bf7a-d91a883bed2f)


### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('lion.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:
![Screenshot 2024-02-15 030708](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/e6a5f595-6c73-43c3-9b1a-ee4869a5974c)


### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("lion.jpg",1)
img = cv2.resize(img,(200,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### Output:

![Screenshot 2024-02-15 031124](https://github.com/r-sathish-02/COLOR_CONVERSIONS_OF-IMAGE/assets/118787261/cbfa0ce4-43ed-4995-821d-0f2ed8e701d5)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







