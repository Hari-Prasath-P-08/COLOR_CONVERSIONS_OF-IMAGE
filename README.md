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
### Developed By: Hari Prasath. P
### Register Number: 212223230070

### i) Read and display the image

<br>
```python
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("GSLV - Mark III.png",1)
cv2.imshow("display window",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
print(img.shape)
```
<br>

### Output:

![Screenshot 2024-02-21 221713](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/df85aebf-274c-4ea2-9af5-0eecd48f9672)


### ii)Write the image

<br>
```python
img1=cv2.imread("GSLV - Mark III.png",0)
cv2.imshow("display window",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('greyscale.jpeg',img1)
```
<br>

### Output:

![Screenshot 2024-02-21 221821](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/02423db0-b1a7-47b8-b7df-b3b7a6544202)


### iii)Shape of the Image

<br>
```python
import cv2
img1=cv2.imread("GSLV - Mark III.png",1)
print(img1.shape)
```
<br>

### Output:

![Screenshot 2024-02-21 221927](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/957b372f-f0d7-41fe-851e-2ff4f8bd7738)


### iv)Access rows and columns
<br>
```python
import random
import cv2
image=cv2.imread('GSLV - Mark III.png',1)
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>

### Output:

![Screenshot 2024-02-21 222019](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/43bfd99c-8336-45a0-a29d-96f0a7f970be)


### v)Cut and paste portion of image
<br>
```python
import cv2
img2 = cv2.imread("GSLV - Mark III.png")
x = 0
y = 200
x1 = 160
y1 = 450
x2 = 0
y2 = 0
cropimg = img2[x:x1+x2, y:y1+y2]
cv2.imshow("Original Image", img2)
cv2.imshow("Cropped Image", cropimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>

### Output:

![Screenshot 2024-02-21 222124](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/0f712665-6999-4fc9-8f06-e26c221d7b83)
![Screenshot 2024-02-21 222156](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/9735ea7e-47a1-461f-b80b-d2ac01ae34e0)


### vi) BGR and RGB to HSV and GRAY
<br>
```python
import cv2
img = cv2.imread('GSLV - Mark III.png',1)
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
<br>

### Output:

![Screenshot 2024-02-21 222321](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/5321daf7-6ebd-4eb2-bb9e-44afe208c0e7)
![Screenshot 2024-02-21 222334](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/4d2ac4c0-6436-4e3a-9401-5c4dcdedb7f4)
![Screenshot 2024-02-21 222344](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/8d889a2f-40a4-4b9f-9ec8-45eb6bf80147)
![Screenshot 2024-02-21 222354](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/2c9e3fac-71ed-4140-ab50-3bc9d79098b8)
![Screenshot 2024-02-21 222410](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/75cc57b4-9f12-4d1a-9cec-7e0862d770a9)


### vii) HSV to RGB and BGR
<br>
```python
import cv2
img = cv2.imread('GSLV - Mark III.png')
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
<br>

### Output:

![Screenshot 2024-02-21 222458](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/c85242eb-fb0c-4785-9546-134692ca62ca)
![Screenshot 2024-02-21 222514](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/b828e9e2-38dc-46f6-b19f-e1fa453d81a1)
![Screenshot 2024-02-21 222523](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/949b6ce8-7c93-4bbe-9e42-01a1376eeb03)


### viii) RGB and BGR to YCrCb
<br>
```python
import cv2
img = cv2.imread('GSLV - Mark III.png')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
<br>

### Output:

![Screenshot 2024-02-21 222626](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/bf2a3d95-6c4c-4041-8b40-85b31c1b28f9)
![Screenshot 2024-02-21 222634](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/6269ba68-e613-4a71-bf46-45a0cdb602e6)
![Screenshot 2024-02-21 222648](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/d44aed65-874e-4560-88e2-84683e92d535)


### ix) Split and merge RGB Image
<br>
```python
import cv2
img = cv2.imread('GSLV - Mark III.png',1)
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
<br>

### Output:

![Screenshot 2024-02-21 222843](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/5d29399b-eee0-45f4-9045-e6c47b27c4b7)
![Screenshot 2024-02-21 222915](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/d60bd137-edd1-409c-b819-c7a27707e60f)
![Screenshot 2024-02-21 222938](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/fc87134d-6f58-4562-8d32-04d23efcd9ae)
![Screenshot 2024-02-21 222948](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/17923204-bd7b-42c4-9a87-161035dafab0)


### x) Split and merge HSV Image
<br>
```python
import cv2
img = cv2.imread("GSLV - Mark III.png",1)
img = cv2.resize(img,(300,200))
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
<br>

### Output:

![Screenshot 2024-02-21 223039](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/f0423f93-458e-4547-98e2-19c683396e17)
![Screenshot 2024-02-21 223052](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/9deaa52c-b2af-4fed-95b6-67f850a6f393)
![Screenshot 2024-02-21 223102](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/f6deb6b7-7ed1-444b-bd99-c661c4980f02)
![Screenshot 2024-02-21 223119](https://github.com/Hari-Prasath-P-08/COLOR_CONVERSIONS_OF-IMAGE/assets/139455593/9df004c5-6019-4629-b26e-3e511db08a2f)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







