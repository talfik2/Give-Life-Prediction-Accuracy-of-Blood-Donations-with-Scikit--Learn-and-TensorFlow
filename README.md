# Give-Life-Prediction-Accuracy-of-Blood-Donations-with-Scikit--Learn-and-TensorFlow
In this repository, I measured prediction accuracy of  Blood Donations in Taiwan(2007) with Scikit- Learn and TensorFlow libraries.
I took the data from DataCamp's Give Life: Predict Blood Donations project with my premium account.(https://learn.datacamp.com/projects/646)

# DATASET

Our dataset is from a mobile blood donation vehicle in Taiwan. The Blood Transfusion Service Center drives to different universities and collects blood as part of a blood drive. We want to measure prediction accuracy of this prediction : whether or not a donor will give blood the next time the vehicle comes to campus.

# SCIKIT LEARN

In Scikit - Learn, I splitted the Training and Test Datasets by  train_test_split() method of from sklearn.model_selection.

Then, I fitted our model to Logistic Regression by sklearn.linear_model 's LogisticRegression.

After that, trained our ML model by .score() method.

Then, I testes our ML model again by .score() method. To test our model, I could use sklearn.metrics'saccuracy_score but both of them do the same thing is by inspecting the SK Learn source code. Turns out that the .score() method in the LogisticRegression class directly calls the sklearn.metrics.accuracy_score method.

ın the end, we had 0.7700534759358288 accuracy with Scikit Learn.


# TENSORFLOW

In TensorFlow, first of all,I  splitted this dataset into training and test data by Pandas' iloc() method and chose eval parts by Pandas' pop() function.

Secondly, I created input functions to supply data for training, evaluating, and prediction.

After that, I defined a feature column, that is an object describing how the model should use raw input data from the features dictionary.
For transfusion data, the 2 raw features are numeric values, so we'll build a list of feature columns to tell the Estimator model to represent each of the four features as 32-bit floating-point values. 

Then, I instantiated an estimator. In this step, I used tf.estimator.DNNClassifier.

After that, I trained my model by .train() method. As a result of this step, my Loss value is 0.48.

Then, I evaluated my model by .evaluate() method. 

As a result of my evaluation, I had 0.809 Test set accuracy.

My result is 0.809 with TensorFlow.
It is 0.770 with Scikit-Learn.
I increased  the accuracy 3.9 % . It may seem a little change, but for M.L. models, even little changes can create big differences.
