# Iowa Home Data Analysis
Code I wrote to learn basic and intermediate machine learning skills. I trained and validated a model for Iowa home sale prices predictions. I also created a pipeline for this model.

The steps to building and using a model are:

* Define: What type of model will it be? A decision tree? Some other type of model? Some other parameters of the model type are specified too.
* Fit: Capture patterns from provided data. This is the heart of modeling.
* Predict: Just what it sounds like
* Evaluate: Determine how accurate the model's predictions are.

### Types of Data:
* Training Dataset: The sample of data used to fit the model. Usually approximately ~70% of the total data.
* Validation Dataset: The sample of data used to provide an unbiased evaluation of a model fit on the training dataset while tuning model hyperparameters. The evaluation becomes more biased as skill on the validation dataset is incorporated into the model configuration. Used to make sure that after fiting the model with training data set, we haven't overfit/underfit, so essentially used to fine tune the initial fitting done by training dataset. Usually approximately ~20% of the total data.
* Test Dataset: The sample of data used to provide an unbiased evaluation of a final model fit on the training dataset. Used to calculate the mean absolute error (ie, use the model to predict the y-values of the testing data given the x-values; then, compare the predicted y-values to the actual y-values in the testing data). We want to have low MAE in a good model.

### Pipelines:
Pipelines are a simple way to keep your data preprocessing and modeling code organized. Specifically, a pipeline bundles preprocessing and modeling steps so you can use the whole bundle as if it were a single step.

Many data scientists hack together models without pipelines, but pipelines have some important benefits. Those include:

1. Cleaner Code: Accounting for data at each step of preprocessing can get messy. With a pipeline, you won't need to manually keep track of your training and validation data at each step.
2. Fewer Bugs: There are fewer opportunities to misapply a step or forget a preprocessing step.
3. Easier to Productionize: It can be surprisingly hard to transition a model from a prototype to something deployable at scale. 
4. More Options for Model Validation: You will see an example in the next tutorial, which covers cross-validation.

### Building a pipeline steps:
#### Step 1: Define Preprocessing Steps

 Similar to how a pipeline bundles together preprocessing and modeling steps, we use the ColumnTransformer class to bundle together different preprocessing steps. The code should:

  *   impute missing values in numerical data, and
  *   impute missing values and applies a one-hot encoding to categorical data.

#### Step 2: Define the Model
Next, we define a random forest model with the familiar RandomForestRegressor class.

#### Step 3: Create and Evaluate the Pipeline
Finally, we use the Pipeline class to define a pipeline that bundles the preprocessing and modeling steps. There are a few important things to notice:

* With the pipeline, we preprocess the training data and fit the model in a single line of code. (In contrast, without a pipeline, we have to do imputation, one-hot encoding, and model training in separate steps. This becomes especially messy if we have to deal with both numerical and categorical variables!)
* With the pipeline, we supply the unprocessed features in X_valid to the predict() command, and the pipeline automatically preprocesses the features before generating predictions. (However, without a pipeline, we have to remember to preprocess the validation data before making predictions.)
