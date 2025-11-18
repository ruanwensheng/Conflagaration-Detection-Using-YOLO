# Conflagaration-Detection-Using-YOLO
## 🎥 YOLOv11 Vehicle Detection Demo
<p align="center">
<img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/3ff3c463-42cc-44ca-8996-13fc43e198e4" />
<img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/1d1ce44e-2002-4ea6-814e-c7cd4036aabd" />
<img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/92d5682a-62b8-4a37-94d3-068c75cb177b" />
</p>

## Train YOLO Models With Google Colab

Click below to acces a Colab notebook for training YOLO models. It makes training a custom YOLO model as easy as uploading an image dataset and running a few blocks of code.

<a href="https://colab.research.google.com/github/ruanwensheng/License-Plate-Detection-Using-YOLOv11-/blob/main/License_Plate_Detection.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
## Results
<img width="2400" height="1200" alt="results" src="https://github.com/user-attachments/assets/8234ad7e-b83b-4569-90dd-a93a3fafe90b" />


---

### Evaluations

| Criteria                     | Evaluation |
|-----------------------------|------------|
| **Training Trend**          | Losses decrease steadily without spikes |
| **Overfitting**             | None observed; val loss aligns with train loss |
| **Localization Accuracy**   | High: **mAP50 ≈ 95%** |
| **General Detection Quality** | Improving: **mAP50-95 ≈ 22%** |
| **Precision**               | Rising trend, reaches ~55% |
| **Recall**                  | Rising trend, reaches ~52% |
| **Fit for Detection Task**  | Decent – can detect, but needs improvement for fine accuracy |

---


## Deploy YOLO Models
The `yolo_detect.py` script provides a basic example that shows how to load a model, run inference on an image source, parse the inference results, and display boxes around each detected class in the image. This script shows how to work with YOLO models in Python, and it can be used as a starting point for more advanced applications. 

To run inference with a yolov11 model on a USB camera at 1280x720 resolution, issue:

```
python yolo_detect.py --model yolov11.pt --source usb0 --resolution 1280x720
```

Here are all the arguments for yolo_detect.py:

- `--model`: Path to a model file (e.g. `my_model.pt`). If the model isn't found, it will default to using `yolov8s.pt`.
- `--source`: Source to run inference on. The options are:
    - Image file (example: `test.jpg`)
    - Folder of images (example: `my_images/test`)
    - Video file (example: `testvid.mp4`)
    - Index of a connected USB camera (example: `usb0`)
    - Index of a connected Picamera module for Raspberry Pi (example: `picamera0`)
- `--thresh` (optional): Minimum confidence threshold for displaying detected objects. Default value is 0.5 (example: `0.4`)
- `--resolution` (optional): Resolution in WxH to display inference results at. If not specified, the program will match the source resolution. (example: `1280x720`)
- `--record` (optional): Record a video of the results and save it as `demo1.avi`. (If using this option, the `--resolution` argument must also be specified.)


### Deploy on Raspberry Pi
The Raspberry Pi 4 and 5 are just powerful enough to run nano and small-sized YOLO models in real time. The article linked below walks through how to run YOLO models on the Raspberry Pi.

[How to Run YOLO Detection Models on the Raspberry Pi](https://www.ejtech.io/learn/yolo-on-raspberry-pi)
