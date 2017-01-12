# SelfDriving-Vehicle
Machine Learning predicting Steering angle from a dash mounted camera Images &amp; Videos

##Dependencies
The following are the dependencies you should install.

* [Keras](https://github.com/fchollet/keras/)
* [TensorFlow](https://www.tensorflow.org/versions/r0.10/get_started/os_setup.html)
* [OpenCV](http://opencv.org/downloads.html)

## Models and Tasks

#### Prediction with deep learning

The specific task here is to predict driving speed from a dashboard-mounted camera; there's tons of this data open-sourced by the folks at comma.ai [here](https://github.com/commaai/research).

1. **Static CNN** -- The model is based off of NVIDIA's ["End-to-end Self-driving" model](https://arxiv.org/abs/1604.07316). The resulting model is in ```models/cnn_prediction.py```.
2. **CNN + LSTM** -- In order to incorporate temporal info into the static CNN, I experimented with several architectures discussed in ["Beyond Short Snippets: Deep Networks for Video Classification"](http://arxiv.org/abs/1503.08909). The resulting model is in ```models/cnn_lstm_prediction.py```.
3. **Optical flow** -- Tracking feature points with sparse optical flow implicitly encodes temporal dependencies between frames. 

## Datasets

A few places to find open-source data to play with:

* https://www.cityscapes-dataset.com/
* http://robotcar-dataset.robots.ox.ac.uk/examples/
* http://selfracingcars.com/blog/2016/7/26/polysync
* http://data.selfracingcars.com/
* http://research.comma.ai/
