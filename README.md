---
description: Back to basics
---

# Basic ML Knowledge



### Data Splits

In machine learning, data is typically split into three subsets: training, validation (eval), and test sets.

#### Training Data

The training set is used to fit the parameters of the machine learning model. The model "learns" the patterns and relationships between the features and target variables from this data.

#### Validation Data (eval)

The validation set is used to tune the hyperparameters of the model (e.g. number of layers in a neural network, regularization parameters, etc.) and evaluate its performance during the training process. It provides an unbiased estimate of the model's skill on data that was not used for training. The validation set is sometimes referred to as ...

#### Testing Data

The test set is a data sample that is completely held out and not used at all during the training process. It is used to provide an unbiased evaluation of the final model's performance after it has been fully trained and tuned. The test set represents the data that the model will encounter when deployed in the real world. Sometimes the test set is called the "holdout set".



The key differences are:

* Training set trains the model parameters
* Validation set tunes hyperparameters and evaluates during training
* Test set evaluates the final, tuned model's performance

#### Why do we split data?



**Random Sampling**



### **Overfitting**



### **Underfitting**



### **Understanding Training Loss**

Loss goes up =

Loss goes down =

Loss doesnt move =

### **Regularization**





