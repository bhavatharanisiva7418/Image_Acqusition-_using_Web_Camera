
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
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()




## ii) Display the video
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()



## iii) Display the video by resizing the window

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()



## iv) Rotate and display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
## Output

### i) Write the frame as JPG image

![Screenshot 2025-03-29 014501](https://github.com/user-attachments/assets/8131a922-f27b-4aa4-942d-47d52b3af836)

### ii) Display the video

![Screenshot 2025-03-29 014744](https://github.com/user-attachments/assets/9c5dd739-bf18-4352-b36c-86c53663c571)


### iii) Display the video by resizing the window

![Screenshot 2025-03-29 015901](https://github.com/user-attachments/assets/5d06caa4-1603-4ea9-85c9-73c54782402f)




### iv) Rotate and display the video

![Screenshot 2025-03-29 015413](https://github.com/user-attachments/assets/2544bcfe-16eb-465c-bdaf-77fb2ffa6903)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
