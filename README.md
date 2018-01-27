# How_to_simulate_a_self_driving_car

## Overview

This is the code for [this](https://youtu.be/EaY5QiZwSP4) video on Youtube by Siraj Raval. We're going to use Udacity's [self driving car simulator](https://github.com/udacity/self-driving-car-sim) as a testbed for training an autonomous car. 

## Dependencies

You can install all dependencies by running one of the following commands

You need a [anaconda](https://www.continuum.io/downloads) or [miniconda](https://conda.io/miniconda.html) to use the environment setting.

```python
# Use TensorFlow without GPU
conda env create -f environments.yml 

# Use TensorFlow with GPU
conda env create -f environment-gpu.yml
```

Or you can manually install the required libraries (see the contents of the environemnt*.yml files) using pip.


## Usage


### Run the pretrained model

Start up the Udacity self-driving simulator for [Linux](https://d17h27t6h515a5.cloudfront.net/topher/2017/February/58983558_beta-simulator-linux/beta-simulator-linux.zip), [Mac](https://d17h27t6h515a5.cloudfront.net/topher/2017/February/58983385_beta-simulator-mac/beta-simulator-mac.zip), or [Windows](https://d17h27t6h515a5.cloudfront.net/topher/2017/February/58983318_beta-simulator-windows/beta-simulator-windows.zip); choose a scene and press the Autonomous Mode button.  Then, run the model as follows:

```python
python drive.py model.h5
```

### To train the model

You'll need the data folder which contains the training images.

```python
python model.py
```

This will generate a file `model-<epoch>.h5` whenever the performance in the epoch is better than the previous best.  For example, the first epoch will generate a file called `model-000.h5`.


## Troubleshoot


### Run the pretrained model

If you got the error about import numpy, re-install the numpy:
```command
pip uninstall numpy
pip install numpy
```

### To train the model

If you got the error about different dimension of input, change the dimension coresponding with your data pictures' dimension base on the resolution you run for the train data. Open utils.py file and change "IMAGE_HEIGHT, IMAGE_WIDTH":

```Details
IMAGE_HEIGHT, IMAGE_WIDTH, IMAGE_CHANNELS = 66, 200, 3
```


## Credits

The credits for this code go to [naokishibuya](https://github.com/naokishibuya). I've merely created a wrapper to get people started.



