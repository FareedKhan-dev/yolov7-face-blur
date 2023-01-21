<img src="https://pjreddie.com/media/image/yologo_2.png" width="100"/>

<img src="https://img.shields.io/badge/python-3.9.0-blue.svg"> <img src="https://img.shields.io/badge/license-MIT-blue.svg">

# yolov7-face-blur

This repository is created on top of two repository
1. [Object Blurring by RizwanMunawar](https://github.com/RizwanMunawar/yolov7-object-blurring)
2. [Face detction by derronqi](https://github.com/derronqi/yolov7-face)

____

#### How to install
1. Create Virutal Environment of Python, Recommended python version `3.9.0`, incase you dont have `3.9.0`, see `pyenv` guide.
2. Activate the Environment using `python -m venv your_env_name/Scripts/activate`
3. install required libraries using `pip install -r requirements`
4. (Optional) If you want to use GPU, you have to install additional requirements i.e, `pip install -r requirements_gpu.txt` 
_____

Models:

| Models           |  Test Size | Easy  | Medium | Hard  | FLOPs (B) @640 | Google | Baidu |
| -----------------| ---------- | ----- | ------ | ----- | -------------- | ------ | ----- |
| yolov7-lite-t    | 640        | 88.7  | 85.2   | 71.5  |  0.8           | [google](https://drive.google.com/file/d/1HNXd9EdS-BJ4dk7t1xJDFfr1JIHjd5yb/view?usp=sharing) | [gsmn](https://pan.baidu.com/s/1oxlJVveUgHUQs4UiR26aCw) |
| yolov7-lite-s    | 640        | 92.7  | 89.9   | 78.5  |  3.0           | [google](https://drive.google.com/file/d/1MIC5vD4zqRLF_uEZHzjW_f-G3TsfaOAf/view?usp=sharing) | [3sp4](https://pan.baidu.com/s/1f_DD1gZ1AUGLFKHoPNq10Q) |
| yolov7-tiny      | 640        | 94.7  | 92.6   | 82.1  |  13.2          | [google](https://drive.google.com/file/d/1Mona-I4PclJr5mjX1qb8dgDeMpYyBcwM/view?usp=sharing) | [aujs](https://pan.baidu.com/s/1IzHLQc2RbPyuDgEqgY8hUg) |
| yolov7s          | 640        | 94.8  | 93.1   | 85.2  |  16.8          | [google](https://drive.google.com/file/d/1_ZjnNF_JKHVlq41EgEqMoGE2TtQ3SYmZ/view?usp=sharing) | [w72z](https://pan.baidu.com/s/1fZfZTH7qSdN-0zTk5iCcnA) |
| yolov7           | 640        | 96.9  | 95.5   | 88.0  |  103.4         | [google](https://drive.google.com/file/d/1oIaGXFd4goyBvB1mYDK24GLof53H9ZYo/view?usp=sharing) | [jrj6](https://pan.baidu.com/s/1PiEnSaogvjkNvRLHctBz9A) |
| yolov7+TTA       | 640        | 97.2  | 95.8   | 87.7  |  103.4         | [google](https://drive.google.com/file/d/1oIaGXFd4goyBvB1mYDK24GLof53H9ZYo/view?usp=sharing) | [jrj6](https://pan.baidu.com/s/1PiEnSaogvjkNvRLHctBz9A) |
| yolov7-w6        | 960        | 96.4  | 95.0   | 88.3  |  89.0          | [google](https://drive.google.com/file/d/1U_kH7Xa_9-2RK2hnyvsyMLKdYB0h4MJS/view?usp=sharing) | - |
| yolov7-w6+TTA    | 1280       | 96.9  | 95.8   | 90.4  |  89.0          | [google](https://drive.google.com/file/d/1U_kH7Xa_9-2RK2hnyvsyMLKdYB0h4MJS/view?usp=sharing) | - |

_______

#### Required Arguments to run

1. `--weights` contains your downloaded model from the above table
2. `--bluurratio` to determine the strength of blurring, default value is `20`
3. `--device` either `cpu` or `0` in case of `gpu`.
4. `--source` containes your images (png, jpg etc) or video (mp4 etc)

______

#### Examples
    # Example with detected accuracy (usng CPU)
    python detect.py --weights yolov7-tiny.pt --blurratio 50 --device cpu --source myimage.jpg

<img src="https://github.com/FareedKhan-dev/yolov7-face-blur/blob/master/example-1.jpg" width="500"/>
    
    # Example with hiding detected area, only blur (usng CPU)
    python detect.py --weights yolov7-tiny.pt --blurratio 50 --hidedetarea --device cpu --source myimage.jpg

<img src="https://github.com/FareedKhan-dev/yolov7-face-blur/blob/master/example-2.jpg" width="500"/>

    # Example on video (usng CPU)
    python detect.py --weights yolov7-tiny.pt --blurratio 50 --hidedetarea --device cpu --source myvideo.mp4
    
<img src="https://github.com/FareedKhan-dev/yolov7-face-blur/blob/master/example-3.gif" width="500"/>
