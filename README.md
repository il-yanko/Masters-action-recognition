# Masters-action-recognition
This project is based on Leap Motion finger joints data. It is recorded, saved as a CSV file, preprocessed, and then used for Deep Learning model training. 
The DL model: LSTM (Long Short Term Memory) neural network.

The UltraLeap (the company that developed the Leap Motion) created SDKs (Software Development Kits) using the framework library. The most up-to-date version for Python is Leap Motion Orion 3.2.1. By default, this version works only with Python 2.7 (it is considered outdated, but the last version that works with this Python SDK as of 2022).

To set up the Leap Motion driver to collect your data, you will need to follow the steps:
1. Go to the Leap Motion webpage, download and install the Leap Motion Orion 3.2.1 SDK;
2. Save the following files to the same folder of your project code: Leap.py, Leap.pyc, Leap.dll, LeapPython.pyd;

Installation of Python-2 environment in Anaconda prompt:
```
conda create −n py2 python=2.7
conda activate py2
conda install numpy pandas notebook
```

Data collection:
1) Connect the Leap Motion already to your computer via a USB connector;
2) Open the notebook LeapMotion_Recorder.ipynb;
3) When you run it, you will be able to collect the data captured by the Leap Motion.
4) When you finish acquiring the gesture or hand motion, press [ENTER] in the Python terminal, and save your data in the file data1.csv.

Model training:
1) Install Python-3 environment;
```
conda create −n py3lm python=3.9 pandas numpy keras tensorflow
conda activate py3lm
```
2) Use LeapMotion_Classifier.ipynb to train the classifier.
Since the data that comprehends a gesture is represented with time series, the coordinates of the fingers change over time, the classier, should be capable of dealing with such data. In this example, I use the widely used model LSTM. 
