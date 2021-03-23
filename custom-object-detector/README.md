- [Installation](#installation)
  - [Install basic - python=2.7 and Tnesorflow=2.2.0](#install-basic---python27-and-tnesorflow220)
  - [TensorFlow Object Detection API Installation](#tensorflow-object-detection-api-installation)
    - [Downloading the TensorFlow Model Garden](#downloading-the-tensorflow-model-garden)
    - [Protobuf Installation/Compilation](#protobuf-installationcompilation)
    - [COCO API installation](#coco-api-installation)
    - [Install the Object Detection API](#install-the-object-detection-api)
    - [Test your Installation](#test-your-installation)
# Installation
## Install basic - python=2.7 and Tnesorflow=2.2.0
## TensorFlow Object Detection API Installation
### Downloading the TensorFlow Model Garden
```
git clone git@github.com:tensorflow/models.git
```
### [Protobuf](protogbuf) Installation/Compilation
```
cd models/research 
# From within TensorFlow/models/research/
protoc object_detection/protos/*.proto --python_out=.
```
### COCO API installation
As of TensorFlow 2.x, the pycocotools package is listed as a dependency of the Object Detection API. Ideally, this package should get installed when installing the Object Detection API as documented in the Install the Object Detection API section below, however the installation can fail for various reasons and therefore it is simpler to just install the package beforehand, in which case later installation will be skipped.
```
git clone https://github.com/cocodataset/cocoapi.git
cd cocoapi/PythonAPI
make
cp -r pycocotools <PATH_TO_TF>/TensorFlow/models/research/
```
if it is not work, replace python with python3 in Makefile and run the following command in the Terminal.
```
pip install cython
or
sudo ARCHFLAGS="-arch x86_64" make install
```
### Install the Object Detection API
Installation of the Object Detection API is achieved by installing the object_detection package. This is done by running the following commands from within Tensorflow\models\research:
```
# From within TensorFlow/models/research/
cp object_detection/packages/tf2/setup.py .
python -m pip install .
```
### Test your Installation
To test the installation, run the following command from within Tensorflow\models\research:
```
# From within TensorFlow/models/research/
python object_detection/builders/model_builder_tf2_test.py
``` 

