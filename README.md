# IMPLEMENTATION-OF-OPENING-AND-CLOSING-Using-OpenCV
# Aim:
To implement Opening and Closing using Python and OpenCV.

# Software Required:
Anaconda - Python 3.7  
OpenCV
# Algorithm:
## Step1:
Import the necessary packages.

## Step2:
Create the Text using cv2.putText.

## Step3:
Create the structuring element.

## Step4:
Use Opening operation.

## Step5:
Use Closing Operation.

# Program:
```
Developed By: YUVARAJ V
Register No.: 212223230252
```
```py
# Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create the text using cv2.putText
def load():
    img = np.ones((600,600), dtype=np.uint8)
    cv2.putText(img, text='DIPT', org=(25, 350), fontFace=cv2.FONT_HERSHEY_SIMPLEX, fontScale=8, color=(255, 255, 255), thickness=25)
    return img

def display_img(img):
    plt.imshow(img,cmap='gray')

img = load()
display_img(img)

white_noise = np.random.randint(0,5,size=(600,600))
white_noise

white_noise = white_noise * 225
noise_img = white_noise + img

plt.imshow(noise_img,cmap='gray')

noise_img = noise_img.astype(np.uint8)
kernal = np.ones((5,5), dtype = np.uint8)

# Use the Opening Operation
opening = cv2.morphologyEx(noise_img, cv2.MORPH_OPEN, kernal)
plt.imshow(opening, cmap = 'gray')

# Use the Closing Operation
close_img = cv2.morphologyEx(noise_img,cv2.MORPH_CLOSE,kernal)
plt.imshow(close_img,cmap='gray')
```

# Output:
### Input image:   
<img width="420" height="413" alt="image" src="https://github.com/user-attachments/assets/e318a125-9bd4-4568-910f-fefcb0cecf78" />

### Adding White Noise:   
<img width="411" height="407" alt="image" src="https://github.com/user-attachments/assets/ae038cce-326a-4fbf-ae5b-849db51158db" />

### Opening:
<img width="408" height="402" alt="image" src="https://github.com/user-attachments/assets/9a65ec3e-fe7a-4f6c-a5fc-62317b4d5bdb" />

### Closing:
<img width="409" height="407" alt="image" src="https://github.com/user-attachments/assets/576c77b7-c24a-456c-89c7-c75007c75a27" />

# Result:
Thus the Opening and Closing operation is used in the image using python and OpenCV.

