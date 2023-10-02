# Neural Network Model

---

## Overview

The purpose of this analysis was to see if I could build a neural network model that could predict if applcants  
would be successful if they were funded by Alphabet Soup. Before standardizing the data with the `StandardScaler`  
module, I dropped the non-beneficial columns ('EIN' and 'NAME' ) and then binned unique columns from the  
'CLASSIFICATION' and 'APPLICATION_TYPE' columns to help drop the total amount of columns to look through.  
I then split, fit, and transformed the data with the `train_test_split` function and standardized the data with  
Standard Scaler. The first pass through my model, I defined the model and added in 2 hidden layers with their  
activations and an output layer with only 1 unit. I then compiled, trained, and evaluated that model to see  
how well it predicted the test data. I did the same process again 3 more times.  

---

## Results

  ### Model 1:
  * The target was the 'IS_SUCCESSFUL' column.
  * The features were the rest of the columns.
  * The columns that were dropped were the 'NAME' and 'EIN'.

  * Input features were 43 because it was all the feature columns.
  * There were 2 hidden layers
      * Layer 1 had 80 units and relu as an activation.
      * Layer 2 had 30 units and relu as an activation.
      * I set the activation to relu to have a more advanced activation in the hidden layers than the output layer.
  * The Output layer has 1 unit and sigmoid as an activation.
  * I trained the model with 100 epochs.

  * The loss was `0.5565` and the accuracy was `0.7258`.
  * I was not able to achieve the performance of a 0.75 or higher on this model.

---

  ### Model 2:
  * The target was the 'IS_SUCCESSFUL' column.
  * The features were the rest of the columns.
  * The columns that were dropped were the 'NAME' and 'EIN'.

  * Input features were 45 because it was all the feature columns.
  * There were 3 hidden layers
      * Layer 1 had 200 units and tanh as an activation.
      * Layer 2 had 150 units and relu as an activation.
      * Layer 3 had 100 units and relu as an activation.
  * The  Output layer had 1 unit and sigmoid as an activation.
  * I trained the model with 100 epochs.

  * The loss was `0.5687` and the accuracy was `0.7246`.
  * I was not able to achieve the performace of a 0.75 or higher. The things I had changed in this model was
    my binning of the 'CLASSIFICATION' column by adding in one more column. I also used tanh as the first
    activation and it seemed to work better with this data, but not by much. I then added in a third hidden
    layer thinking it would help be more precise when filtering through all the data. I lastly increased the
    number of neurons in the first and second layer thinking it needed more neurons to be more accurate.

<img width="594" alt="Screenshot 2023-10-01 at 7 16 32 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/dba6ed47-059b-4d6a-b7ba-13ae8802e9f8">  


<img width="587" alt="Screenshot 2023-10-01 at 7 16 39 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/1f843297-bab7-4f58-a4f2-220757bac48a">

---

  ### Model 3:
  * The target was the 'IS_SUCCESSFUL' column.
  * The features were the rest of the columns.
  * The columns that were dropped were the 'NAME' and 'EIN'.

  * I set the `test_size` to 0.5.  

  * Input features were 45 because it was all the feature columns.
  * There were 2 hidden layers
      * Layer 1 had 90 units with tanh as an activation.
      * Layer 2 had 80 units with relu as an activation.
  * The Output layer had 1 unit and sigmoid as an activation.
  * I trained the model with 50 epochs.

  *  The loss was `0.5592` and the accuracy was `0.7267`.
  *  I was not able to achieve the performance of a 0.75 or higher. I removed a hidden layer seeing as
     the last model was worse than the first one and thought it could be because I had an extra hidden layer.
     I also thought that my test and train data split could be the issue so I wanted to see what a bigger test
     size would do, if the model could better predict the test data. I lessed the amount of neurons per hidden
     layer because I thought that it could be overfitting with too many units. Lastly I trained the daya with
     only 50 epochs because it seemed the longer it trained, the model would stall and even go down a bit.

<img width="579" alt="Screenshot 2023-10-01 at 7 18 56 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/652da229-1eee-4c20-9259-806e76a15267">

<img width="581" alt="Screenshot 2023-10-01 at 7 19 03 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/f9cb6ebe-6ac1-4b0f-8039-29b9415b5e72">

---

  ### Model 4:
  * The target was the 'IS_SUCCESSFUL' column.
  * The features were the rest of the columns.
  * The columns that were dropped were the 'NAME' and 'EIN'.

  * I set the `test_size` to 0.4.  

  * Input features were 45 because it was all the feature columns.
  * There were 4 hidden layers
    * Layer 1 had 100 units and tanh as an activation.
    * Layer 2 had 80 units and leaky_relu as an activation.
    * Layer 3 had 50 units and tanh as an activation.
    * Layer 4 had 50 units and leaky_relu as an activation.
  * The Output layer has 1 unit and sigmoid as an activation.
  * I trained the model with 10 epochs.

  * The loss was `0.5516` and the accuracy was `0.7284`.
  * I was not able to achieve the performance of a 0.75 or higher, however, this was the highest accuracy I've had so
    far. I had added in 2 more hidden layers and played around with leaky_relu as an activation to see if it was a
    better fit than the relu. I then changed the test size to 0.4 and lessened the amount of neurons per layer.
    I think the thing that helped a lot was the number of epochs being so low. I noticed the higher the amount of
    epochs were, the lower the accuracy was.

<img width="570" alt="Screenshot 2023-10-01 at 7 21 11 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/26cf3fa7-063d-455c-9f38-19dc44288b40">

<img width="573" alt="Screenshot 2023-10-01 at 7 21 17 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/a4fff939-37da-410a-9fda-21f131f4f4a7">

---
## Final Model

  * The target was the 'IS_SUCCESSFUL' column.  
  * The features were the rest of the columns.  
  * The column that was dropped was 'EIN'.

  * Input features were 252 because it was all the feature columns.
  * There were 2 hidden layers
    * Layer 1 had 10 units and relu as an activation.
    * Layer 2 had 20 units and relu as an activation.
  * The Output layer has 1 unit and sigmoid as an activation.
  * I trained the model with 50 epochs.
  * The loss was `0.4593` and the accuracy was `0.7784`.
  * I got my model to get above 75%! I look at my other models and realized I needed more training data, not less.
    I added in the 'NAMES' column that I had previously dropped and my first few attempts at this model, I got 0.74.
    I saw that I probably needed a lot more data from the 'NAMES' column so I added in more and binned the rest as
    'Other'. I also saw that my units for each model were fairly high so I wondered what a drastic decrease in them
    would do and it seems like that is what this model needed.

<img width="546" alt="Screenshot 2023-10-01 at 9 01 25 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/bd0002e4-9248-4781-af50-386343648e53">

<img width="563" alt="Screenshot 2023-10-01 at 9 01 30 PM" src="https://github.com/Kaileycar/deep-learning-challenge/assets/130424499/e5522860-d93c-4189-8a58-4f370d3cd90a">

---

## Summary

After 6 modeling attempts, I finally got my last model to reach a 77% accuracy. The model was losing a lot of its data  
by dropping the 'NAME' column, which helped drastically in a higher prediction and lower loss. Relu seemed to be the best  
activation function for the hidden layers and sigmoid for the output. I found that 2 hidden layers gave the best results  
with fewer neurons per layer. I'm sure if there were more than 50 epochs, the model could be a tiny bit better, however  
at around 50 epochs, the accuracy started to go back and forth and not a straight linear decrease.


