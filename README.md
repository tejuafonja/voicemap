# voicemap

This repository contains code to build deep learning models to identify
different speakers based on audio samples containg their voice.

The eventual aim is for this repository to become a pip-installable
python package for quickly and easily performing speaker identification
related tasks.

**This tensorflow/Keras/python2.7 branch is discontinued. Work is
continuing on the pytorch-python-3.6 branch which will become the
master branch.**

## Instructions
#### Requirements
Make a new virtualenv and install requirements from `requirements.txt`
with the following command.
```
pip install -r requirements.txt
```
This project was written in Python 2.7.12 so I cannot guarantee it works
on any other version.

#### Data
Get training data here: http://www.openslr.org/12
- train-clean-100.tar.gz
- train-clean-360.tar.gz
- dev-clean.tar.gz

Place the unzipped training data into the `data/` folder so the file
structure is as follows:
```
data/
    LibriSpeech/
        dev-clean/
        train-clean-100/
        train-clean-360/
        SPEAKERS.TXT
```

Please use the `SPEAKERS.TXT` supplied in the repo as I've made a few
corrections to the one found at openslr.org.

#### Libcudnn.so.7 error?
This is a tensorflow-gpu related error. Tensorflow-gpu < 1.13.0 requires CUDA 9.0. You can follow the installation procedure on [tensorlow website](https://www.tensorflow.org/install/gpu). If you have the cuda version already installed, you should set the `$LD_LIBRARY_PATH`. 

```
export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
```

#### Run tests

This requires the LibriSpeech data.
```
python -m unittest tests.tests
```

## Contents
### voicemap
This package contains re-usable code for defining network architectures,
interacting with datasets and many utility functions.

### experiments
This package contains experiments in the form of python scripts.

### notebooks
This folder contains Jupyter notebooks used for interactive
visualisation and analysis.
