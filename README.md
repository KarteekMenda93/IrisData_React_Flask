# IrisData_React_Flask

It's a template on which we can build a React app and call Flask to make predictions.

1. The front-end is developed in React and would include a single page with a form to submit the input values
2. The back-end is developed in Flask which exposes prediction endpoints to predict using a trained classifier and send the result back to the front-end for easy consumption

## Creation of model
I trained a DecisionTreeClassifier on the iris dataset which requires 4 features — Sepal Length, Sepal Width, Petal Length and Petal Width. Then, I saved the model to `classifier.joblib` using joblib.dump(). The classifier can now be used to predict on new data.

## Creation of Flask to give the predictions for the data
The Flask app has a POST endpoint /prediction. It accepts the input values as a json, converts it into an array and returns to the UI. In actual application, we’ll use the same data to make prediction using the classifier stored in `classifier.joblib` and return the prediction. The entire code for this Flask can be found in `aap.py`

Now run it on local host. Now this will start up the service on  `127.0.0.1:5000`.

## Creation of React app UI
The form is made up of columns inside rows. Thus, as I have 4 features, I added 2 columns in 2 rows. The first row will have dropdowns for Sepal Length and Sepal Width. The second row will have dropdowns for Petal Length and Petal Width. I began by creating a list of options for each of these dropdowns. You can refer `App.js` for this.

Inside app.css, change the link of the background image to your own. I added an image of flowers from `Unsplash`. I also updated the title to Iris Plant Classifier and the page title too inside `index.html` file in the `public folder`.

The application is now ready to use the model. Restart both services after building the UI using `npm run build`. The application looks like below:

https://github.com/KarteekMenda93/IrisData_React_Flask/blob/main/Capture.PNG

