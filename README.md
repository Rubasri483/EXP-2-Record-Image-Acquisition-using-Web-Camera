# EXP.2-RECORD-IMAGE-ACQUISTION-USING-WEB-CAMERA


## NAME: Rubasri R
## REG.NO: 212224240139

## AIM

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the captured frame as a JPG file.
2. Display the live video.
3. Display the video by resizing the frame.
4. Rotate and display the video.

## SOFTWARE REQUIRED

- Anaconda – Python 3.7
- Jupyter Notebook
- OpenCV (`cv2`)
- Matplotlib
- IPython

## ALGORITHM

## Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

## Step 2:
Capture frames from the webcam.

## Step 3:
Save a captured frame as a JPG image using `cv2.imwrite()`.

## Step 4:
Display the live video by capturing and displaying frames continuously.

## Step 5:
Resize the captured frames using `cv2.resize()` and display the resized video.

## Step 6:
Rotate the video frames using `cv2.rotate()` and display the rotated video.

---

# PROGRAM

## i) Write the Frame as JPG File

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("Captured_frame.jpg", frame)

cap.release()

captured_image = cv2.imread('Captured_frame.jpg')

plt.imshow(captured_image[:, :, ::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

## ii) Display the Video

```python
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
```

## iii) Display the Video by Resizing the Window

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (100, 150))

    frame_rgb = cv2.cvtColor(
        resized_frame,
        cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

## iv) Rotate and Display the Video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(
        frame,
        cv2.ROTATE_90_CLOCKWISE
    )

    frame_rgb = cv2.cvtColor(
        rotated_frame,
        cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()

    time.sleep(0.05)

cap.release()
```

---

# OUTPUT

### i) Write the Frame as JPG Image

<img width="588" height="429" alt="image" src="https://github.com/user-attachments/assets/9d792d3f-e654-4ab9-a2ff-6251e51e06b0" />


### ii) Display the Video

<img width="552" height="410" alt="image" src="https://github.com/user-attachments/assets/3cc72d40-4692-4da1-8d3d-aab2113474ed" />


### iii) Display the Video by Resizing the Window

<img width="464" height="401" alt="image" src="https://github.com/user-attachments/assets/a51cc5f3-5530-4252-8b54-ca70d70f3081" />


### iv) Rotate and Display the Video


<img width="363" height="398" alt="image" src="https://github.com/user-attachments/assets/d9d81dfe-4cc2-45f5-861c-c1f73b529899" />

---

## RESULT

Thus, an image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
