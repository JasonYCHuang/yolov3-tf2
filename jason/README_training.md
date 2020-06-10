# Training from scratch

### 0. Install

```bash
$ docker run --gpus all -it --rm -v $(pwd):/tf tensorflow/tensorflow:latest-gpu-py3-jupyter bash

:/tf# pip install -r requirements.txt
```


### 1. Download Dataset

You can read the full description of dataset [here](http://host.robots.ox.ac.uk/pascal/VOC/)
```bash
$ wget http://host.robots.ox.ac.uk/pascal/VOC/voc2012/VOCtrainval_11-May-2012.tar -O ./data/voc2012_raw.tar
$ mkdir -p ./data/voc2012_raw
$ tar -xf ./data/voc2012_raw.tar -C ./data/voc2012_raw
$ ls ./data/voc2012_raw/VOCdevkit/VOC2012 # Explore the dataset
```




