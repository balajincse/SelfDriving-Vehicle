## Prediction models

The prediction models here use Keras with TensorFlow backend, and make use of some OpenCV tools.

### Speed prediction with CNN+LSTM

This is to implement some of the architectures described in ["Beyond Short Snippets: Deep Networks for Video Classification"](http://arxiv.org/abs/1503.08909) in an effort to incorporate temporal information as an improvement over the static CNN model below.

The model in cnn_lstm_prediction.py is three convolution layers (each extended in the time dimension), flatten and fully-connected layers, stacked stateful recurrent (LSTM) layers, and a final full-connected layer for the output; more details in the comments [here](https://github.com/BoltzmannBrain/self-driving/blob/master/models/cnn_lstm_prediction.py#L88). Example invocations are at the top of the model script.


### Speed prediction with CNN

The aim of this project is to train a deep CNN model to learn driving speeds from a dashboard camera such that it can be used for predicting speeds in the future. Please see cnn_prediction_model.py for model details on the model and experiment design.

To train:

```
./cnn_prediction.py -v <path to test video> -d <path to truth data>
```

To test the model:

```
./cnn_prediction.py --test --skipTraining -v <path to test video> -d <path to truth data>
```

The test results will be written to "speed_test.json" and plotted, and the RMSE will be calculated.
