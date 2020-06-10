# Infer byy default

```bash
$ docker run --gpus all -it --rm -v $(pwd):/tf yolov3-tiny bash
```

```bash
:/tf# python detect.py --weights ./checkpoints/yolov3-tiny.tf --tiny --image ./data/007.jpg
```

- - -

## OLD - Building process

### 0. Install

```bash
# yolov3-tiny
$ wget https://pjreddie.com/media/files/yolov3-tiny.weights -O data/yolov3-tiny.weights
```

```bash
# omit --rm for the later commit
$ docker run --gpus all -it -v $(pwd):/tf tensorflow/tensorflow:latest-gpu-py3-jupyter bash

# fix opencv loading error
:/tf# apt-get update
:/tf# apt-get install -y libsm6 libxext6 libxrender-dev
:/tf# pip install -r requirements.txt
```

##### 0.1. Preprocess tiny-weight (optional)

```bash
# first time to preprocess tiny-weight...
:/tf# python convert.py --weights ./data/yolov3-tiny.weights --output ./checkpoints/yolov3-tiny.tf --tiny
```

### 1. Predict

```bash
:/tf# python detect.py --weights ./checkpoints/yolov3-tiny.tf --tiny --image ./data/007.jpg
```

### 2. Commit docker image

```bash
$ docker commit a3f1d2bfab7d yolov3-tiny

$ docker system prune
```