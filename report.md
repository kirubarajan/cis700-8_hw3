# Homework 3: Natural Language Understanding

TODO: add instances of model performing incorrect classification for sentiment classifier and BERT classifier

## Sentiment Classifier
Using the most positive candidate (according to TextBlob) yields the following accuracies:

```
2016 validation accuracy: 
0.5777659005879209

2018 validation accuracy: 
0.558879694462126

2016 test accuracy: 
0.5740245857830037
```

Which is not too impressive, considering that flipping a coin would yield a similar accuracy (~50%)

TODO: finish implementing classification based off of average context sentiment (i wrote the code to compute average sentiment, so just use if/else statements for difference between options and average context sentiment)

## BERT Classifier
Using the vanilla MLP with a ReLU non-linearity, we were able to yield the following accuracies:

```
2016 validation accuracy: 
0.6472474612506681

2018 validation accuracy: 
0.6543602800763845

2016 test accuracy: 
0.6563335114911811
```

Adding an extra layer, with a size of 128 and ReLU activation gave the following results:

```
2016 validation accuracy: 
0.5531801175841796

2018 validation accuracy: 
0.5493316359007002

2016 test accuracy: 
0.55264564404062
```

This didn't make sense to us, since this is deep learning and more layers equals more performance (/s). So, after changing the learning rate from 0.001 to 0.002 and doubling the number of training steps to 20,000, we yielded the following accuracies:

```
2016 validation accuracy: 
0.6419027258150721

2018 validation accuracy: 
0.642266072565245

2016 test accuracy: 
0.6451095670764297
```

Which was closer to the original vanilla MLP. Finally, we decided to add Dropout after the input layer to prevent any sort of overfitting. In respose, we also increased the learning rate and number of steps to yield:

```
2016 validation accuracy: 
0.649919828968466

2018 validation accuracy: 
0.6499045194143858

2016 test accuracy: 
0.6557990379476216
```

### *Cheating* with the Validation Set
When we train using the validation set with the included vanilla MLP code, we yield the following accuracies:

```
2016 test accuracy: 
0.69000534473543561
```

Increasing the first layer to have a size of 1000 yielded a small accuracy improvement:

```
2016 test accuracy: 
0.7022982362373063
```

Increasing the number of number of training examples from validation set by 1000, and training for 30,000 steps yields the following accuracies:

```
0.7183324425440941
```

Finally, adding another dense layer of size 128 with ReLU activation gives us the following results:

```
2016 test accuracy: 
0.7017637626937466
```
