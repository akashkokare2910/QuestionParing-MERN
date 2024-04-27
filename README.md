# Quora Question Pairing system

![](https://img.shields.io/badge/node-v14.15.3-brightgreen)
![](https://img.shields.io/badge/npm-v6.14.9-green)
![](https://img.shields.io/badge/react.js-^17.0.1-lightblue)
![](https://img.shields.io/badge/database-mongoDB-brightgreen)
![](https://img.shields.io/badge/mongoose-^5.11.18-green)
![](https://img.shields.io/badge/express.js-^4.17.1-blue)
![](https://img.shields.io/badge/cors.js-^2.8.5-brown)
![](https://img.shields.io/badge/python-^3.7.7-yellow)
![](https://img.shields.io/badge/Frontend-HTML/CSS/JS-lightgrey)
![](https://img.shields.io/badge/license-MIT-brown)

### Mernstack Machine Learning Application

This is a full-stack web-based machine learning application designed to determine if two input or selected questions share similar meanings or intents.

#### Features:

- Predicts if two input questions have the same meaning/intent.
- Stores input questions in a MongoDB database.
- Renders questions stored in the database in the UI.
- Allows users to select any two questions from a list and predict their similarity.

### Technologies used:

- Frontend:- `React.js` and `Material UI`
- Backend: - `Nodejs`, `Express.js`, `MongoDB`
- Machine Learning:- `Python`, `Ensemble Learning Algorithms`, `Data Analysis`

#### How the Application Works:

- User submits two input questions, which are stored in the database..
- The questions are simultaneously passed as parameters to a Python script.
- The Python script processes the input and predicts the result.
- The predicted result is rendered in the UI.
- Questions from the database are fetched using the get() method and re-rendered in the UI.
- If the user selects any two questions from the rendered list, they are processed on the server side, and the result is displayed.

To run the python script on server side I have used Nodejs' `child_process()` method.

![Cosine similarity](./images/display.gif)

or click [here](https://www.youtube.com/watch?v=68Nq_IlLZ8o) to see video demo.

#### Now Machine Learning part:

- Dataset is taken from [Kaggle](https://www.kaggle.com/c/quora-question-pairs)
- The final training data was prepared after doing some cleaning(removing punctuation, stemming, lemmatisation, etc) and preprocessing(cosine similarity, polarity, question length, etc).
- I have used python's `nltk` library to do the preprocessing.
- Feature Engineering: to generate features out of the cleaned and preprocessed data.
- To train the model I have use lightGBM, RandomForest and XGBoost algorithm. And out of all three XGBoost performs best.
- So, XGBoost model was selected as the final for prediction.
- Model evaluation metric: Log Loss. Log loss from XGBoost 0.428

##### How Cosine Similarity works:

Cosine similarity is a metric used to measure how similar the documents are irrespective of their size. Mathematically, it measures the cosine of the angle between two vectors projected in a multi-dimensional space. The cosine similarity is advantageous because even if the two similar documents are far apart by the Euclidean distance (due to the size of the document), chances are they may still be oriented closer together. The smaller the angle, higher the cosine similarity.

To read more click [here](https://www.machinelearningplus.com/nlp/cosine-similarity/)

![Cosine similarity](./images/cosine_similarity.PNG)

##### How Polarity works:

Polarity analysis takes into account the amount of positive or negative terms that appear in a given sentence. It is useful to some extent, since it does a good job of structuring data sets.
If two questions have different polarity they have more chances of being different or vice-versa.

To read more click [here](https://www.quora.com/What-is-polarity-and-subjectivity-in-sentiment-analysis).

##### To run this project on your machine:

- Clone this repository to your local machine.
- Make sure you have `node >= v14.15.3` installed.
- To install the dependencies run `npm install` .
- run the above command in the backend folder too.
- Now to start server run `nodemon server` in he backend folder.
- To start app run `npm start` in another terminal.
- To run the python script you must have `python >= 3.7` installed.
- Make sure your server is running before asking the app to predict.
