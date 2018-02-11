# ALPR-OpenCV

Using OpenCV libraries to build an automatic number plate recognition system.

**NOTE:  This is an experimental project and is incomplete in a number of ways.** *This project is for be test it in Windows 10 64bits, and the code has been modify to generate licence plate patterns from **Ecuador**.*

## Dependencies:

- [Python v3.6.+ (64bits)](https://www.python.org/downloads/)
- NumPy v1.14.+
- OpenCV v3.14.+ (for cv2)
- h5py v2.7.+
- keras v2.1.+
- MatPlotLib v2.1.+
- [TensorFlow v1.+](https://www.tensorflow.org/install/install_windows)

## Installations

Note: For install libraries use CMD terminal.

1. Download Python 3.6.+ (last version **of 64bits**), and install it. [Guide Video](https://www.youtube.com/watch?v=gSjL3K8C8Ao)
2. Installing numpy library (if not included)
```
py -m pip install numpy
```
3. Installing OpenCV library
```
py -m pip install opencv-python
```
4. Installing Keras library
```
py -m pip install keras
```
5. Installing h5py library
```
py -m pip install h5py
```
6. Installing MatPlotLib
```
py -m pip install matplotlib
```
7. Installing TensorFlow (CPU or GPU) library
```
#*CPU version*
py -m pip install --upgrade tensorflow
```
or
```
#*GPU version*
py -m pip install --upgrade tensorflow-gpu
```


## Project

Create a folder name `anpr` and copy the following py files and folders:
- `bgs\` (backgrounds images)
- `fonts\` (ttf file)
- `test\` (generated licence plate, _empty_)
- `common.py` (Common variables)
- `model.py` (py dependencie)
- `gen.py` (For generate test set images)
- `train.py` (For train the model with generate images)
- `detect.py` (For test result)


## Using Networks

Usage is as follows:

1. (optional but recommended) `./extractbgs.py SUN397.tar.gz`: Extract ~3GB of background images from the [SUN database](http://groups.csail.mit.edu/vision/SUN/) into `bgs/` (`bgs/` must be empty). The tar file (36GB) can be [downloaded here](http://vision.princeton.edu/projects/2010/SUN/SUN397.tar.gz). This step may take a while as it will extract 108,634 images.

2. `./gen.py`: Locate variable `generate_amount ` and set the number you want (default 100), it will safe the test set images in `test/` (`test/`must be empty). This step requires a `.ttf` files to be in the `fonts/` directory.

3. `./train.py`: Train the model. A **GPU** is recommended for this step. It will take around 100,000 batches to converge. When you're satisfied that the network has learned enough press Ctrl+C once and the process will create a `weights.npz` file and write the weights.

4. `./detect.py in.png CPUweights.npz out.png`: Detect number plates in an image and give and output image. if get a tensorflow gpu error, you should uninstall it `py -m pip unistall tensorflow-gpu`


Reproduce: [Deevoluation](https://github.com/Deevoluation/ALPR)
