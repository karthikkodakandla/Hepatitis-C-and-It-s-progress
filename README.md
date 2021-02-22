
Presence of Hepatitis C and It's Progress _Karthik Kodakandla_Cu2592
Built a Deep Learning Model to predict the presence of Hepatitis C  and it's progress. In the first basic model though the accuracy is more (88%) , all predictions are made with only one class( Blood Donor) as the dataset is imbalanced. This will be considered as naive model. As our main aim is to find the presence of Hepatitis c and it's progress importance should be given for the classes which predict hepatitis C(class 1 to 4). So i have used oversampling method to train the deep learning model on all classes equally. With this i have achieved good prediction and also there are predictions in other classes including a class where only 7 records exists.

Preprocessing Data:
1.Features and Target Label: Category column is target variable and we will consider all remaining columns as features. 
2.Unnamed:0 is Id column and will not be useful for prediction so we can remove it from the analysis.
3.Missing Values : I have checked for the missing values in the data. There are few missing values so we have imputed the missing values with the mean of the respected columns.
4.Split data: Splitted data with training features(x_train) , training_label(y_train) , validation_features(x_test) and validation_label(y_test)
5.Oversampling : as we have imbalanced data set, we used oversampling method on training data to resample the data to get equal number of classes with out any bias. This will help to model training data with equal importance on all clases.

Build Model:
Built Keras model with metrics accuracy and recall as both will have equal importance on prediction. Accuracy to show the overall correct predictions and recall to show if the preictions made on all classes with out any bias
