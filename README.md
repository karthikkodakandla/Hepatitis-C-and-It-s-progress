
<h2>Presence of Hepatitis C and It's Progress </h2>

This is a Deep learning Model to predict the presence of Hepatitis C  and it's progress

The reason to chose this project is that the labels are highly imbalnced . Label Count are as below:

0(Blood Donor =            533

3(Cirrhosis) =            30

1(Hepatitis) =          24

2(Fibrosis) =       21

0(suspect Blood Donor)  =       7

![alt text](https://github.com/karthikkodakandla/Hepatitis-C-and-It-s-progress/blob/master/download.png "Histogram")

<h3>Breif about the project</h3>

Built a Deep Learning Model to predict the presence of Hepatitis C  and it's progress. In the first basic model though the accuracy is more (88%) , all predictions are made with only one class( Blood Donor) as the dataset is imbalanced. This will be considered as naive model. As our main aim is to find the presence of Hepatitis c and it's progress importance should be given for the classes which predict hepatitis C(class 1 to 4). So i have used oversampling method to train the deep learning model on all classes equally. With this i have achieved good prediction and also there are predictions in other classes including a class where only 7 records exists.

<h3>Preprocessing Data:</h3>

1.Features and Target Label: Category column is target variable and we will consider all remaining columns as features. 

2.Unnamed:0 is Id column and will not be useful for prediction so we can remove it from the analysis.

3.Missing Values : I have checked for the missing values in the data. There are few missing values so we have imputed the missing values with the mean of the respected columns.

4.Split data: Splitted data with training features(x_train) , training_label(y_train) , validation_features(x_test) and validation_label(y_test)

5.Oversampling : as we have imbalanced data set, we used oversampling method on training data to resample the data to get equal number of classes with out any bias. This will help to model training data with equal importance on all clases.

<h3>Build Model:</h3>
Built Keras model with metrics accuracy and recall as both will have equal importance on prediction. Accuracy to show the overall correct predictions and recall to show if the preictions made on all classes with out any bias

2. a) 1 Hidden Layer vs 2 Hidden Layers
1.Compared Keras model with 1 hidden layer and 2 hidden layers. model with one hidden layer is best when compared with the two hidden layers.
2.With two hidden layers we are increasing the capacity. As this is not complex model increasing hidden layers will not help much 

2. b) No of neurons in hidden layers between (a)2/3 the size of the input layer, plus the size of the output layer, and twice the size of the input layer
1. compared Keral models with basic model( normalized model) with 2/3 size of the input layer plus the size of the output layer which is 13 neurons and twice the size of the input layer which is 24 neurons. We are basically increasing width of the model. 
Accuracy of basic model with 8 neurons : 94.47%          Recall of basic model        : 84.55%
Accuraciy of model with 13 neurons     : 93.82%          Recall of model(13 neurons)  : 82.11%
Accuracy of model with 24 neurons      : 95.12%          Recall of model (24 neurons) : 87.80%

Based on the graph and above metrics(accuracy and recall) the best model will be model with 24 neurons. But in general we can see that both models over fit as the gap between training and validation increases. We need use regularization to solve this issue in the next models.

2. c) Regularization
1. created keras model by introducing l1 regularization and l2 regularization. L2 Regularization is best comapred with l1 regularization here. here as the inputs are less l1 regularization may not be much helpfull. both baseline and l1 regularization are overfitting compared to l2 regulariation model

Accuracy of basic model                  : 94.47%          Recall of basic model               : 84.55%
Accuraciy of model l1_regularization     : 95.28%          Recall of model(l1_regularization)  : 86.18%
Accuracy of model l2_regularization      : 96.26%          Recall of model (l2_regularization ): 90.24%


