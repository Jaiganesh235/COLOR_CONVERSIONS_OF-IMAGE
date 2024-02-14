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
### Step1:Choose an image and save it as a filename.jpg ,
### Step2:Use imread(filename, flags) to read the file.
### Step3:Use imshow(window_name, image) to display the image.
### Step4:Use imwrite(filename, image) to write the image.
### Step5:End the program and close the output image windows.
### Step6:Convert BGR and RGB to HSV and GRAY
### Step7:Convert HSV to RGB and BGR
### Step8:Convert RGB and BGR to YCrCb
### Step9:Split and Merge RGB Image
### Step10:Split and merge HSV Image

##### Program:
```
### Developed By:Sivaram R
### Register Number: 212222100050
```
<table>
  <tr>
    <td width=50%>


### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('but.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('but',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td>
    
#### OUTPUT:
![1](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/eaf79d84-f5b3-40a4-8e3e-1650a4d49ec7)
</td>
</tr>



<tr>
  <td width=50%>


### ii)Write the image
```Python
    import cv2
    image=cv2.imread('but.jpg',0)
    cv2.imwrite('mini.jpg',image)
```
  </td>
  <td>

#### OUTPUT:
![2](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/0a033122-b82e-401f-8aef-2044f790d074)

</td>
</tr> 
<tr> 
  <td width=50%>

### iii)Shape of the Image
```Python
     import cv2
    image=cv2.imread('but.jpg',1)
    print(image.shape)
```
  </td> 
  <td>

#### OUTPUT:
![3](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/526d6206-8a6f-457e-8fe7-d08f63774dad)

  </td>
  </tr> 
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
     import random
     import cv2
     image=cv2.imread('moun.jpg',1)
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
![4](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/9cbbe1b4-6bad-4049-bd26-418595bf9f40)

 </td>
 </tr>
 <tr>
  <td width=50%>

### v)Cut and paste portion of image
```Python
     import cv2
     image=cv2.imread('moun.jpg',1)
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
![5](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/7561656f-271a-4187-81e9-e30ce8fe7394)
 </td>
 </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
    import cv2
    img = cv2.imread('moun.jpg',1)
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

![6](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/5853421a-fc05-48b6-9ece-75883ff3352f)

### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('moun.jpg')
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

![7](https://github.com/sivaram-R/COLOR_CONVERSIONS_OF-IMAGE/assets/121165794/2fb232c7-f68c-48c8-8679-27bb35941929)

### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('moun.jpg')
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

![Uploading 8.png…]()

### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('moun.jpg',1)
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

![deepikasrinivasan DIPT5](https://github.com/deepikasrinivasans/COLOR_CONVERSIONS_OF-IMAGE/assets/119393935/50393780-01e4-4523-840d-f7282e980faf)


### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("moun.jpg",1)
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

![deepikasrinivasan DIPT6](https://github.com/deepikasrinivasans/COLOR_CONVERSIONS_OF-IMAGE/assets/119393935/1b066b61-0ee9-45c5-abd4-b8df5e8966dd)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.






