# IrisData_React_Flask

It's a template on which we can build a React app and call Flask to make predictions.

1. The front-end is developed in React and would include a single page with a form to submit the input values
2. The back-end is developed in Flask which exposes prediction endpoints to predict using a trained classifier and send the result back to the front-end for easy consumption

## Creation of model
I trained a DecisionTreeClassifier on the iris dataset which requires 4 features — Sepal Length, Sepal Width, Petal Length and Petal Width. Then, I saved the model to classifier.joblib using joblib.dump(). The classifier can now be used to predict on new data.

## Creation of Flask to give the predictions for the new data
The Flask app has a POST endpoint /prediction. It accepts the input values as a json, converts it into an array and returns to the UI. In actual application, we’ll use the same data to make prediction using the classifier stored in `classifier.joblib` and return the prediction. The entire code for this Flask can be found in `aap.py`

Now run it on local host. Now this will start up the service on 127.0.0.1:5000.


