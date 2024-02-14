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
### Step1: Choose an image and save it as a filename.jpg ,
### Step2: Use imread(filename, flags) to read the file.
### Step3: Use imshow(window_name, image) to display the image.
### Step4: Use imwrite(filename, image) to write the image.
### Step5: End the program and close the output image windows.
### Step6: Convert BGR and RGB to HSV and GRAY
### Step7: Convert HSV to RGB and BGR
### Step8: Convert RGB and BGR to YCrCb
### Step9: Split and Merge RGB Image
### Step10: Split and merge HSV Image

##### Program:
```
### Developed By: S.JAIGANESH
### Register Number: 212222240037
```
<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('jai.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('photography by jai',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:

![Screenshot (289)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/442b3dbd-310c-4fe1-8c78-a4e75ab31424)

  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('jai.jpg',0)
    cv2.imwrite('news.jpg',image)
```
  </td>
  <td>

### OUTPUT:

![Screenshot (290)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/a4c8ac4c-ed3c-4ea3-a598-4c4cd4295af4)

  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('jai.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![Screenshot (291)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/809e3b36-d123-4a4a-8837-b20a3325afc6)


  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('jai.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
        for j in range(image.shape[1]):
            image[i][j]=[random.randint(0,255),
                         random.randint(0,255),
                         random.randint(0,255)] 
    cv2.imshow('particular image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
  </td>
  <td width="50%">

### OUTPUT:
![Screenshot (292)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/336efc58-a8f3-432c-a62a-b570dfd3eed3)

  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
   import cv2
   image=cv2.imread('jai.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('particular image 1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:

![Screenshot (293)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/6357e70e-f148-4ebe-ae84-5bc88cad3c57)

  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('jai.jpg',1)
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

### OUTPUT:
![Screenshot (294)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/67b2d842-0a63-43cc-a1b4-0ca1dc6c592a)


### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('jai.jpg')
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

### OUTPUT:

![Screenshot (295)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/5426875a-fe70-479e-b834-76019182c807)



### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('jai.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:

![Screenshot (296)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/df16a437-f9b8-4f06-8e0a-7bfa47639201)



### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('jai.jpg',1)
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

### OUTPUT:
![Screenshot (297)](https://github.com/Jaiganesh235/COLOR_CONVERSIONS_OF-IMAGE/assets/118657189/9e2ca3e4-d940-4a11-91dc-7bf8b637f016)




### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("niru.jpg",1)
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

### OUTPUT:

![WhatsApp Image 2024-02-13 at 09 35 01_9654fe31](https://github.com/niraunjana/COLOR_CONVERSIONS_OF-IMAGE/assets/119395610/701243fd-9e61-42fc-b829-2f6d4955cca1)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
