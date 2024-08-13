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

### Developed By: Thrinesh Royal.T
### Register Number: 212223230226

<table>
  <tr>
    <td width=50%>


### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('dog',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
#### OUTPUT:
![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/777feaf4-1d28-4f52-a8cd-1e422087a2f1)
</td>
</tr>



<tr>
  <td width=50%>


### ii)Write the image
```Python
    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('new1.jpg',image)
```
  </td>
  <td>

#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/ce57f1da-8e11-41c3-acb0-b621066f67d6)
</td>
</tr> 
<tr> 
  <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('dog.jpg',1)
    print(image.shape)
```
  </td> 
  <td>

#### OUTPUT:
![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/ea9f4f60-00d5-45b3-8105-d0d9a2447a6d)
  </td>
  </tr> 
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
     import random
     import cv2
     image=cv2.imread('dog.jpg',1)
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
  </td>
  <td width="50%">

#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/838de8f1-b2c8-4ae4-8526-dd131a71b88a)

 </td>
 </tr>
 <tr>
  <td width=50%>

### v)Cut and paste portion of image
```Python
     import cv2
     image=cv2.imread('dog.jpg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
  </td>
  <td>

#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/0f017783-5046-4786-b369-3d176636ae6d)
 </td>
 </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('dog.jpg',1)
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
#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/fd212e0b-69a2-4b41-81d0-658bfb9d0ed0)

### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('dog.jpg')
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
#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/bbf9e68f-9b13-4800-8f0c-45aa829e4440)

### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/2a38bd31-bad1-4e12-b177-aca1d6dade4e)


### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('dog.jpg',1)
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
#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/57a975bf-70c8-438c-b162-63021b31c7be)


### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("dog.jpg",1)
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
#### OUTPUT:

![image](https://github.com/SANTHAN-2006/COLOR_CONVERSIONS_OF-IMAGE/assets/80164014/aca549ca-140c-4367-a9bb-5fcd8d541ac7)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.






