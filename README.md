
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Import CV2,numpy and the other required libraries

### Step 2:
<br>
Create an instance of Video Capture and save the displayed image

### Step 3:
Capture video and using numpy resize the shape of the window and display the video
<br>

### Step 4:
Rotate the captured image by 180*
<br>


## Program:
``` Python
### Developed By:BHAVATHARANI S
### Register No:212223230032

## i) Write the frame as JPG file
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    if not ret:
        break
    cv2.imshow("Webcam", frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()



## ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Iswarya',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import numpy as np
capture = cv2.VideoCapture(0)
while True:
    ret,frame=capture.read()
    if not ret:
        break
    height,width = frame.shape[:2]
    smaller_frame=cv2.resize(frame,(width//2,height//2))
    image = np.zeros((height,width,3),dtype=np.uint8)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame

    cv2.imshow('PIC',smaller_frame)
    
    if cv2.waitKey(1)==ord('q'):
        break
capture.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Iswarya',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
</br>
![Screenshot 2025-03-29 014501](https://github.com/user-attachments/assets/8131a922-f27b-4aa4-942d-47d52b3af836)

</br>


### ii) Display the video
</br>
![Screenshot 2025-03-29 014744](https://github.com/user-attachments/assets/9c5dd739-bf18-4352-b36c-86c53663c571)

</br>


### iii) Display the video by resizing the window
</br>
![Screenshot 2025-03-29 015901](https://github.com/user-attachments/assets/5d06caa4-1603-4ea9-85c9-73c54782402f)

</br>



### iv) Rotate and display the video
</br>
![Screenshot 2025-03-29 015413](https://github.com/user-attachments/assets/2544bcfe-16eb-465c-bdaf-77fb2ffa6903)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
