# Deep Learning Challenge

The purpose of this assignment was to build a neural network model to see if we could predict if applicants  
would be successful if they were funded by Alphabet Soup. Play around with all the hyperparameters to see if  
you could reach an accuracy of 75% or higher. Then write a report discussing your findings and predicting which  
kind of model would accuratley predict if people would be successful or not.  

---

## About 

This assignment is split into 3 sections. Parts 1 and 2 are building your model and testing / evaluating it. Part 3  
is writing up a report on your findings and explaining them. When building and optimizing your models, here are  
some thoughts to consider:      
  * Adjust the input data to ensure that no variables or outliers are causing confusion in the model, such as:
  * Dropping more or fewer columns.
  * Creating more bins for rare occurrences in columns.  
  * Increasing or decreasing the number of values for each bin.
  * Add more neurons to a hidden layer.
  * Add more hidden layers.
  * Use different activation functions for the hidden layers.
  * Add or reduce the number of epochs to the training regimen.
Try to build a model with a 75% or higher accuracy.

---

## Getting Started

1. Grab the [Starter Files](https://github.com/Kaileycar/deep-learning-challenge/files/12778633/Starter_Code.zip)
2. Create a new repository for this project called `deep-learning-challenge`.
3. Clone the new repository to your computer.
4. Inside your local git repository, create a directory for the Notebooks and Models.
5. Create a `md` file for your report.

---

## Usage

**Step 1: Preprocess the Data**  
1. Read in the `charity_data.csv`
2. Drop the `EIN` and `NAME` columns.
3. Bin the `CLASSIFICATION` and `APPLICATION_TYPE` columns and put all the uniuqe values in a separate
   column called `Other`.
4. Split the `X` and the `y` and use the `train_test_split` function.
5. Standardize and transform the training and testing data.


**Step 2: Compile, Train, and Evaluate the Model**  
1. Working in Google Colab, create a neural network model:
     * Determine the number of units and activation functions per layer.
     * Determine the number of hidden layers.
     * Create an Output Layer.
2. Compile and train the model.
3. Evaluate the models loss and accuracy on the test data.
4. Save the model to a `h5` file.


**Step 3: Optimize the Model**  
1. Preprocess the data as above and change the hyperparameters to try to get a better accuracy.
2. Your model should try to achieve an accuracy of 75% or higher.
3. Save your models to a `h5` file.


**Step 4: Write a Report on the Neural Network Model**  
1. Create an Overview describing the purpose of your analysis.
2. Create a Results section which should include your data preprocessing and your compilig, training, and
   evaluation of your model.
3. Create a Summary section which should summarize your overall results and come up with predictions on how
   to make your model better.
