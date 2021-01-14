# Amazon Reviews Sentiment Classification Model Using Spacy

The goal of this project is to train a Convolutional neural network (CNN) within the spacy package by using labeled Amazon Reviews from a [Kaggle Dataset](https://www.kaggle.com/bittlingmayer/amazonreviews). The model was trained and assessed on Google AI Platform. This [Python Reference](https://realpython.com/sentiment-analysis-python/) was used heavily to train and assess the model. A lot of the code from this reference was used directly in this notebook. Once the model is trained using the observations in the dataset (which are labeled as being either positive or negative), I should then be able to determine the sentiment of a new Amazon review that the model has not seen before. 

The data is in a text file where the text of each review is preceeded by either label1 or label2 depending on if the review is positive or negative. The first step invovles reading in the text file and using Pandas to format it into a DataFrame with one column for the review and the other for the label (the sentiment). 

I then added the the textcat pipe to the spacy pipeline, shuffled the dataframe to ensure that data was not ordered in a particular way, and then reduced the size of the training dataset so that the training would only take a few hours.

## Results

I took 10000 observations from the test dataset to evaluate the model. Our precision score was 88.20%, the recall score was 86.45%, and the f-score was 87.32%. This indicates that about 88.2% of the reviews were predicted correctly. While this is a respectable result, I could train a much more accurate model by using all 3.6 million observations from the original dataset. Due to limitations of available computer hardware, I had to limit the number of observations used to train the model to just 10000. 

I also took a random review off of Amazon (a one start review), and the model did correctly classify it as negative.