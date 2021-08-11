# IntroML
Code I wrote to learn basic and intermediate machine learning skills. I trained and validated a model for Iowa home sale prices predictions.

The steps to building and using a model are:

* Define: What type of model will it be? A decision tree? Some other type of model? Some other parameters of the model type are specified too.
* Fit: Capture patterns from provided data. This is the heart of modeling.
* Predict: Just what it sounds like
* Evaluate: Determine how accurate the model's predictions are.

Types of Data:
* Training Dataset: The sample of data used to fit the model. Usually approximately ~70% of the total data.
* Validation Dataset: The sample of data used to provide an unbiased evaluation of a model fit on the training dataset while tuning model hyperparameters. The evaluation becomes more biased as skill on the validation dataset is incorporated into the model configuration. Used to make sure that after fiting the model with training data set, we haven't overfit/underfit, so essentially used to fine tune the initial fitting done by training dataset. Usually approximately ~20% of the total data.
* Test Dataset: The sample of data used to provide an unbiased evaluation of a final model fit on the training dataset. Used to calculate the mean absolute error (ie, use the model to predict the y-values of the testing data given the x-values; then, compare the predicted y-values to the actual y-values in the testing data). We want to have low MAE in a good model.
