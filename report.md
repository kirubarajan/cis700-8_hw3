# Homework 3: Natural Language Understanding

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

### *Cheating* with the Validation Set
When we train using the validation set with the included vanilla MLP code, we yield the following accuracies:

```
2016 test accuracy: 
0.69000534473543561
```
