# arduino-tensorflow-example
Code and results from https://medium.com/p/7daf95b4157

It is important to review and clean up any bad data samples from the training dataset. With good training data the model is making accurate predictions with very high confidence. E.g. alternating flex and punch:
```
punch: 0.000110
flex: 0.999890

punch: 0.999995
flex: 0.000005
```

It would be interesting to see how well the model generalises for other users.

<p align="center">
<img src="https://github.com/robmarkcole/arduino-tensorflow-example/blob/master/images/flex.png" width="800">
</p>

<p align="center">
<img src="https://github.com/robmarkcole/arduino-tensorflow-example/blob/master/images/punch.png" width="800">
</p>

<p align="center">
<img src="https://github.com/robmarkcole/arduino-tensorflow-example/blob/master/images/train.png" width="800">
</p>