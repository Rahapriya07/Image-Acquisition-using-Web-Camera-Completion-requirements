# Experiment No-2: Image Acquisition Using Web Camera
## Name : Raha Priya Dharshini M
## Reg no.: 212224240124

## Aim
To capture an image using a web camera, display live video, resize the video frames, and rotate the video using Python and OpenCV.

## Software Requirements
- Python
- Jupyter Notebook
- OpenCV (`cv2`)
- Matplotlib
- IPython
- Webcam

## Procedure

### i) Capture and Save a Frame as a JPG File
1. Import the required libraries.
2. Initialize the webcam using `cv2.VideoCapture(0)`.
3. Capture a frame from the webcam.
4. Save the captured frame as `captured_frame.jpg` using `cv2.imwrite()`.
5. Release the webcam.
6. Read and display the captured image using Matplotlib.

### ii) Display the Video
1. Initialize the webcam.
2. Capture video frames continuously for a specified number of iterations.
3. Convert each frame from BGR to RGB format.
4. Display the frames using Matplotlib.
5. Clear the previous output to simulate live video.
6. Release the webcam after capturing the frames.

### iii) Display the Video by Resizing the Window
1. Capture frames from the webcam.
2. Resize each frame using `cv2.resize()`.
3. Convert the resized frames from BGR to RGB format.
4. Display the resized video frames using Matplotlib.
5. Release the webcam after the operation.

### iv) Rotate and Display the Video
1. Capture frames from the webcam.
2. Rotate each frame by 90 degrees clockwise using `cv2.rotate()`.
3. Convert the rotated frames from BGR to RGB format.
4. Display the rotated video frames using Matplotlib.
5. Release the webcam after the operation.

## Code
```

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

# i) Write the frame as JPG file

cap = cv2.VideoCapture(0)
ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_frame.jpg", frame)

cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:, :, ::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()


# ii) Display the Video

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


# iii) Display the Video by Resizing the Window

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


# iv) Rotate and Display the Video

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

## Output Screenshots

### i) Captured Image
<img width="1352" height="530" alt="Screenshot 2026-10-26 154603" src="https://github.com/user-attachments/assets/ed17fcd6-17ee-4557-af76-fb07084e20f9" />


### ii) Live Video Display
<img width="1366" height="492" alt="Screenshot 2026-10-26 154627" src="https://github.com/user-attachments/assets/e75158f5-dba1-4354-8eb1-964cb3a0aeae" />

### iii) Resized Video
<img width="1367" height="492" alt="Screenshot 2026-10-26 154642" src="https://github.com/user-attachments/assets/2f1f13cc-f3e7-4d55-a1c5-e0b0b8a9625a" />


### iv) Rotated Video
<img width="1357" height="482" alt="Screenshot 2026-10-26 154701" src="https://github.com/user-attachments/assets/b08a094c-81ef-4871-b328-a424f5b138de" />

## Result
Thus, image acquisition using a webcam was performed successfully. A frame was captured and saved as a JPG file, and video frames were displayed, resized, and rotated using Python and OpenCV.
